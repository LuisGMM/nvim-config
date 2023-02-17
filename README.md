# nvim-config
Config file and steps to install nvim in a debian based system.

## Install neovim

Please refer to the official [neovim installation guide](https://github.com/neovim/neovim/wiki/Installing-Neovim) in case of problems. To install from package use:
```bash
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz &&
tar xzvf nvim-linux64.tar.gz &&
./nvim-linux64/bin/nvim
````
Copy the file `init.lua` into `~/.config/nvim/init.lua`. For that, you can run inside the repo folder:
```bash
mkdir -p ~/.config/nvim &&
touch ~/.config/nvim/init.lua &&
cp ./nvim/init.lua ~/.config/nvim/init.lua
```

After that is installed, run `nvim` to install all default packages & theme.

Make sure you have installed nodejs, npm and all that crap. In doubt:
```bash
sudo apt install curl &&
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash - &&
sudo apt install nodejs &&
node --version &&
npm --version
```

When done, inside neovim, open Mason package manager with `:Mason` and install the preferred packages. In this case, to develop Python, install in this order:
- lua-language-server
- python-lsp-server
- flake8
- isort
- pydocstyle
- mypy
- marksman
- markdownlint

Then, run these commands to finish installing mypy in `plsp`, run inside neovim the following commnand:
```
:PylspInstall pyls-flake8 pylsp-mypy pyls-isort
```

This commnand was taken from [here](https://github.com/williamboman/nvim-lsp-installer/blob/main/lua/nvim-lsp-installer/servers/pylsp/README.md|), a nvim-lsp-installer section dedicated to plsp.


Important links:
- [Third party plugins](https://github.com/williamboman/nvim-lsp-installer/blob/main/lua/nvim-lsp-installer/servers/pylsp/README.md)
- [pslp plugin settings](https://github.com/palantir/python-language-server/issues/190#issuecomment-810880941)

