# dev-env-setup
I use this repository to set up everything I need in a new system or project environment each time.
I use Linux Mint (debian based) as my development OS and Xfce as my desktop.

## git
Install:   
```shell
sudo apt update  
sudo apt install git
```
Setup name and email:
```shell
git config --global user.name "SadeghPouriyanZadeh"
git config --global user.email "pouriyan.sadegh@gmail.com"
```

## gitignore
Setup system-wide:
1. Save .gitignore file to home directory (`~`) as .gitignore
2. Run `git config --global core.excludesfile ~/.gitignore`

## vscode
Setup settings:  
1. Open vscode settings using `Ctrl` + `,` and then settings.json
2. Copy and save `settings.json` content into settings.json file of vscode settings
