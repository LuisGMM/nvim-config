
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

Make sure you have installed the following packages, if not install them:

```bash
pip install mypy flake8 isort pycln autoflake8 autoimport autopep8
```

Make sure you have installed nodejs, npm and all that crap. In doubt:

```bash
sudo apt install curl &&
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash - &&
sudo apt install nodejs &&
node --version &&
npm --version
```
<!-- Install luarocks according to [this documentation](https://github.com/luarocks/luarocks/wiki/Installation-instructions-for-Unix): -->
<!---->
<!-- ```bash -->
<!-- sudo apt install build-essential libreadline-dev unzip && -->
<!-- curl -R -O http://www.lua.org/ftp/lua-5.3.5.tar.gz && -->
<!-- tar -zxf lua-5.3.5.tar.gz                          && -->
<!-- cd lua-5.3.5                                       && -->
<!-- make linux test                                    && -->
<!-- sudo make install                                  && -->
<!-- rm -rf lua-5.3.5 && -->
<!-- wget https://luarocks.org/releases/luarocks-3.8.0.tar.gz && -->
<!-- tar zxpf luarocks-3.8.0.tar.gz && -->
<!-- cd luarocks-3.8.0 && -->
<!-- ./configure --with-lua-include=/usr/local/include && -->
<!-- make && -->
<!-- sudo make install && -->
<!-- rm -rf ../luarocks-3.8.0 -->
<!-- ``` -->

After that is installed, run `nvim` to install all default packages & theme.

When done, inside neovim, open Mason package manager with `:Mason` and install the preferred packages. In this case, to develop Python, install in this order:

- lua-language-server
- pyright
- marksman
- markdownlint
- stylua
- selene

Important links:
- [Third party plugins](https://github.com/williamboman/nvim-lsp-installer/blob/main/lua/nvim-lsp-installer/servers/pylsp/README.md)
