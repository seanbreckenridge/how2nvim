# 01 - Installation

Depending on your operating system there are multiple ways of installing neovim. If you are on Linux
or MacOS you can install it using a package manager; if you are on Windows there is an [installer](https://github.com/neovim/neovim/releases/download/v0.8.1/nvim-win64.zip)
you can download. However, depending on your package manager / Linux distribution you have to look
out for outdated versions. In this guide I'm going over version `0.8.1` which is, as of writing
this, the latest stable release. If your package manager does _not_ have this version, you can
download the [AppImage](https://github.com/neovim/neovim/releases/download/v0.8.1/nvim.appimage) to run the proper version on basically any Linux distribution.

```sh
chmod +x /path/to/nvim.appimage
mv /path/to/nvim.appimage /usr/bin/nvim
```

If you don't want to reach for any of those solutions you can compile it from source as well. It's
easier than it sounds, trust me. Start by cloning the [neovim](https://github.com/neovim/neovim) repository onto your system:

```sh
git clone https://github.com/neovim/neovim
cd neovim
```

Before we can compile however, we need to make sure to install all the [dependencies](https://github.com/neovim/neovim/wiki/Building-Neovim#build-prerequisites). Since I'm
on [Artix Linux](https://artixlinux.org/) I will use the following command from the neovim docs. Make sure you install the
appropriate packages for _your_ system.

```sh
sudo pacman -S base-devel cmake unzip ninja tree-sitter curl
```

Now we can build neovim with the following 2 commands:

```sh
make CMAKE_BUILD_TYPE=Release
sudo make install
```

Check your installation by running `nvim -v` and you should see an output similar to this:

![nvim version check](./gifs/version-check.gif)

Finally, run `:checkhealth` inside of neovim and make sure there are no errors; warnings are fine.
If your installation was successful, you can move on to [the next part](../02-File-Structure/README.md).
