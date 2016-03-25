- Installeer git met git-bash
https://help.github.com/articles/generating-an-ssh-key/
https://help.github.com/articles/working-with-ssh-key-passphrases/

- Installeer virtualbox
- Installeer Vagrant

- Open CommandPrompt en run:
	- mkdir C:\HashiCorp\Vagrant\home
	- setx VAGRANT_HOME "C:\HashiCorp\Vagrant\home"

- Herstart Windows

- Open start menu en typ: "notepad c:\windows\system32\drivers\etc\hosts" sluit af met ctrl+shift+enter
- Voeg de volgende regels toe aan het zojuist geöpende bestand:


- Open git-bash en run (vanuit homedir: ~):
	- vagrant plugin install vagrant-winnfsd
	- git clone git@github.com:Hikariii/homestead.git sldev
	- cd sldev
	- vagrant up
