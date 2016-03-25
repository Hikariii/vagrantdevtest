require 'json'
require 'yaml'

VAGRANTFILE_API_VERSION = "2"
confDir = $confDir ||= File.expand_path(File.dirname(__FILE__) + '/homesteadConf')

homesteadYamlPath = confDir + "/Homestead.yaml"
homesteadJsonPath = confDir + "/Homestead.json"
afterScriptPath = confDir + "/after.sh"
aliasesPath = confDir + "/aliases"

require File.expand_path(File.dirname(__FILE__) + '/homestead/scripts/homestead.rb')

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    if File.exists? aliasesPath then
        config.vm.provision "file", source: aliasesPath, destination: "~/.bash_aliases"
    end

    if File.exists? homesteadYamlPath then
        yaml = File.read(homesteadYamlPath)
        yaml.sub!('%projectroot%', '~/scientadev')
        Homestead.configure(config, YAML::load(yaml))
    elsif File.exists? homesteadJsonPath then
        json = File.read(homesteadJsonPath)
        json.sub!('%projectroot%', File.dirname(__FILE__))
        Homestead.configure(config, JSON.parse(json))
    end

    if File.exists? afterScriptPath then
        config.vm.provision "shell", path: afterScriptPath
    end
end
