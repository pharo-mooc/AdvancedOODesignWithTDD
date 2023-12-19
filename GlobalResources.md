# Some Resources to learn from

- Slides and Videos [https://advanced-design-mooc.pharo.org](https://advanced-design-mooc.pharo.org)

Other sources
- [http://mooc.pharo.org/](http://mooc.pharo.org/)
- [http://books.pharo.org/](http://books.pharo.org/]())

## Git resources

### Slides
- [Resources/Git-PADR-1.2-GitAndDistributedVCS.pdf](Resources/Git-PADR-1.2-GitAndDistributedVCS.pdf)
- [https://github.com/pharo-mooc/AdvancedOODesignWithTDD/tree/main/Resources/Git-PADR-1.3-PracticalGit.pdf](https://github.com/pharo-mooc/AdvancedOODesignWithTDD/tree/main/Resources/Git-PADR-1.3-PracticalGit.pdf)
- [Resources/Git-PADR-2-AdvancedGit.pdf]()
  
### Tutorials
- [Resources/Support-1-BasicGit.pdf](Resources/Support-1-BasicGit.pdf)
- [Resources/Support-2-AdvancedGit.pdf]()
- [Resources/Support-2-PracticalGit.pdf]()
  
## Links
- [http://mooc.pharo.org](a super cool mooc)
- [https://discord.gg/QewZMZa](Pharo discord channel)
- [http://books.pharo.org](Pharo by Example)
- [http://books.pharo.org](Pharo with Style)
- [https://scg.unibe.ch/download/oorp/OORP.pdf](Object-Oriented Reengineering Patterns)

## Optional
- Web [https://rmod-files.lille.inria.fr/?dir=FreeBooks/SeasideBook]()
- Free Books [https://rmod-files.lille.inria.fr/?dir=FreeBooks/SeasideBook]()


## Pharo automatic configuration

You can place a file with whatever.st, in the Preferences folder of your OS (check `self fullName` in the pane of Startup>Version Preferences)

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
Note that we remove the logo so that we can see if the startup action got executed

