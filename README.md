# dev-env-setup

I use this repository to set up everything I need in a new development system or project environment  
Linux Mint (debian based) is my development OS with Xfce as the desktop

## git

1. Install git using apt:

    ```shell
    sudo apt update  
    sudo apt install git
    ```

2. Config name and email:

    ```shell
    git config --global user.name "SadeghPouriyanZadeh"
    git config --global user.email "pouriyan.sadegh@gmail.com"
    ```

## gitignore

1. Save .gitignore file to home directory (`~`) as .gitignore

2. Run `git config --global core.excludesfile ~/.gitignore`

## vscode

1. Open vscode settings using `Ctrl` + `,` and then settings.json

2. Copy and save `settings.json` content into settings.json file of vscode settings

## oh-my-zsh

1. Install zsh first:

    ```shell
    sudo apt update
    sudo apt install zsh
    ```

2. Install oh-my-zsh using [oh-my-zsh website](https://ohmyz.sh/#install) installation command:

    ```shell
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```

3. Logout and login again to see the changes.

    ```shell
    exit
    ```

4. Install plugins by editing `~/.zshrc` file:

    ```shell
    nano ~/.zshrc
    # edit `plugins=(git)` line as below:
    # plugins=(git compleat emoji git-prompt pip sudo ubuntu vscode)
    ```

## uv

1. Install `uv` from [their website](https://docs.astral.sh/uv/):

    ```shell
    sudo apt update
    sudo apt install curl
    curl -LsSf https://astral.sh/uv/install.sh | sh
    uv self update
    ```

2. Identify your shell:

    ```shell
    echo $SHELL
    # `/usr/bin/zsh` = ZSH
    ```

3. Add this alias to `zshrc` config file to customize uv project initialization:

    ```shell
    nano ~/.zshrc
    # add the line below:
    # alias uvinit="uv init && rm hello.py && touch devbook.ipynb"
    ```

4. Reload configuration:

    ```shell
    source ~/.zshrc
    ```

5. Initialize in the project root directory:

    ```shell
    pwd
    # /path/to/root/of/your/project
    # to start a new project
    uvinit
    ```

## conda

1. Install `miniconda` from [miniconda website](https://docs.anaconda.com/miniconda/install/):

    ```shell
    curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    chmod +x Miniconda3-latest-Linux-x86_64.sh
    ./Miniconda3-latest-Linux-x86_64.sh
    # Say **no** to the initialization question
    ```

2. Update conda:

    ```shell
    conda update conda
    ```

3. Create a new environment using `environment.yml` file:

    Default environment name is `ml`.  
    Change `name` field of `environment.yml` file before executing if you want.

    ```shell
    conda env create -f environment.yml
    ```

4. Activate the environment to access system-wide:

    ```shell
    conda activate ml
    ```

    tip: Jupyter loads the kernel as `ml` in any working directory.
