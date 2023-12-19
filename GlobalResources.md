# Some resources to learn from

- Slides and Videos [https://advanced-design-mooc.pharo.org](https://advanced-design-mooc.pharo.org)

Other sources
- [http://mooc.pharo.org/](http://mooc.pharo.org/)
- [http://books.pharo.org/](http://books.pharo.org/)

## Git resources

### Slides
- [Resources/Git-PADR-1.2-GitAndDistributedVCS.pdf](Resources/Git-PADR-1.2-GitAndDistributedVCS.pdf)
- [Resources/Git-PADR-1.3-PracticalGit.pdf](Resources/Git-PADR-1.3-PracticalGit.pdf)
- [Resources/Git-PADR-2-AdvancedGit.pdf]()
  
### Tutorials
- [Resources/Support-1-BasicGit.pdf](Resources/Support-1-BasicGit.pdf)
- [Resources/Support-2-AdvancedGit.pdf](Resources/Support-2-AdvancedGit.pdf)
- [Resources/Support-2-PracticalGit.pdf](Resources/Support-2-PracticalGit.pdf)
  
## Links
- [http://mooc.pharo.org](http://mooc.pharo.org)
- Discord: [https://discord.gg/QewZMZa](https://discord.gg/QewZMZa)
- Pharo by Example, Pharo with Style: [http://books.pharo.org](http://books.pharo.org)
- [Object-Oriented Reengineering Patterns](https://scg.unibe.ch/download/oorp/OORP.pdf)

## Optional
- Web [ A book on Seaside ](https://rmod-files.lille.inria.fr/?dir=FreeBooks/SeasideBook)
- [ A collection of free Books ](http://stephane.ducasse.free.fr/FreeBooks.html)

## Pharo automatic configuration

You can place a file with `whatever.st`, in the Preferences folder of your OS (check `self fullName` in the pane of Startup>Version Preferences)

```
StartupPreferencesLoader default executeAtomicItems: {
	StartupAction 
		name: 'Logo' 
		code: [ PolymorphSystemSettings showDesktopLogo: false] .
	StartupAction 
		name: 'Git Settings' 
		code: [ 
			Iceberg enableMetacelloIntegration: true.
			IceCredentialsProvider sshCredentials
					username: 'git';
					publicKey: '/Users/XXX/.ssh/id_rsa.pub';
					privateKey: '/Users/XX/.ssh/id_rsa'."
			IceCredentialStore current
					storeCredential: (IcePlaintextCredentials new
					username: 'GHUSER';
					password: 'password';
					host: 'github.com';
					yourself).		


			IceCredentialStore current
				storeCredential: (IceTokenCredentials new
					username: 'GHUSER';
					token: 'YOUR TOKEN';
					yourself) 
				forHostname: 'github.com'.
			]. 
}.

```
Note that the script removes the logo so that we can see if the startup action get executed.

