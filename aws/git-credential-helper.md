### Setup the credential helper

Open a command prompt and use Git to run `git config`, specifying 
the use of the Git credential helper with the Amazon credential 
profile, which enables the Git credential helper to send the path 
to repositories:

```bash
git config --global credential.helper '!aws codecommit credential-helper $@'
git config --global credential.UseHttpPath true
```

The Git credential helper writes the following to the .gitconfig file 
```bash
[credential]
	helper = !aws codecommit credential-helper $@
	UseHttpPath = true
```