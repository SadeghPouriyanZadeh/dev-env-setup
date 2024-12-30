# dev-env-setup
I use this repository to set up everything I need in a new system or project environment each time.  
Linux Mint (debian based) is my development OS with Xfce as my desktop.

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

## package and virtual environment management
### For non-Deep-Learning Projects:

1. Install `uv` from [uv website](https://docs.astral.sh/uv/):
```shell
sudo apt update
sudo apt install curl
curl -LsSf https://astral.sh/uv/install.sh | sh
uv self update
```
2. Write an alias to customize uv project initialization.

`alias uvinit="uv init && rm hello.py && touch devbook.ipynb"`

3. Identify your shell and add the alias to its configuration:  
```shell
echo $SHELL
# `/bin/bash` = Bash
nano ~/.bashrc
```

4. Reload configuration:
```shell
source ~/.bashrc
```

5. Initialize the projcet in the project root directory:
```shell
pwd
# /path/to/root/of/your/project
uvinit
```

### For Deep Learning Projects

