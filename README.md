<p align="center">
  <a href="#">
    <img alt="Work With Phoenix" src="https://github.com/Work-With-Phoenix/gatsby-tailwind-startup/raw/main/src/images/phoenix-logo.svg" width="60" style="margin-top: .8rem"/>
  </a>
</p> 
<h1 align="center">
  Github Setup
</h1>
 
The following project consist of a set of bash scripts that you could use to set up the following: 
* Configure your git and github account globally
* Generate your github account SSH Key



## Get your *git* on

1.  **Git config**

Change the email address to yours

```bash

#!/usr/bin/env zsh

#configure your username 
git config --global user.name "username"

#configure your email - must be the same email address directly linked to your github account
git config --global user.email "youremail@here.com"

```

2. **Generate github ssh-key**

Same goes for this section, input your email address.The process is still the same as per the documentation.
```bash
#!/usr/bin/env zsh

#generate ssh-key
ssh-keygen -t ed25519 -C "youremail@here.com"
#add ssh-key to ssh-agent
eval "$(ssh-agent -s)"
#add ssh private key
ssh-add ~/.ssh/id_ed25519
#get the generated ssh key and copy paste it  to your github account
cat ~/.ssh/id_ed25519.pub

```

3. **Generate gpg-key**

The script does its thing up until the last bit which would require manual input.

```bash
#!/usr/bin/env zsh

#generate gpg key pair
gpg --full-generate-key
#list long form of your key
gpg --list-secret-key --keyid-format=long

```


*NOTE* The following scripts are written and pushed  as per the current documentation - timestamp wise


### More Information
If you are a reader like me I'm gonna leave some links to the offical documentations that brought forth the scripts in question.

 - [Generating a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

  - [Generating a new GPG key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

  **Tip:** *If you want to still be on the repo while going through the documentations just hit CTRL+Click to Open Link in New Tab*
 




