# .dotfiles (Ubuntu)

The term "dotfiles" refers to a user's personal configurations to various programs they have running on their system. These configurations respectively are for Ubuntu.

## Table of Contents

- [.dotfiles (Ubuntu)](#dotfiles-ubuntu)
  - [Start Here](#start-here)
  - [Initial Setup](#initial-setup)
    - [Automatic](#automatic)
    - [Manual](#manual)
  - [Installing/Uninstalling dotfiles](#installinguninstalling-dotfiles)
  <!-- - [Installing Packages](#installing-packages) -->

---

## Start Here

This installation method intelligently makes use of [GNU Stow](https://www.gnu.org/software/stow/), which is required for installation. If you do not already have this package, install it.

> **Note:** If you're not already familiar with stow, I highly recommend learning how to make use of it on Unix-like systems whether you're a professional or a power user.

```bash
apt install stow
```

You will also need Git.

```bash
apt install git
```

Clone this repo into your `$HOME` directory using SSH and `cd` into it.

```bash
git clone git@github.com:shawnkhoffman/.dotfiles-ubuntu.git
cd .dotfiles-ubuntu
```

## Initial Setup

### Automatic

Simply run the [setup.sh](/setup.sh) script and follow the instructions at the prompt.

You will first be asked if you want to initialize the submodules for this repo. This is a prerequisite for installing most of the dotfiles.

Once the initial setup is complete, it will give you the option of automatically starting the installer script ([installer.sh](/installer.sh)).

### Manual

Initialize the git submodules from within the root of the repo.

```bash
git submodule update --init --recursive
```

## Installing/Uninstalling dotfiles

After the initial setup is complete, installing/uninstalling is a very straightforward process; simply execute the [installer.sh](/installer.sh) script and follow the instructions at the prompt.

---

<!-- ## Installing Packages

The [/packages](/packages) directory contains two lists of all the packages that I use on Ubuntu.

This assumes you use both pacman for official packages and yay for AUR packages. Install packages from pacman and AUR:

```bash
cd packages/
pacman -S --noconfirm --needed - < .pacman.list && yay -S --noconfirm - < .aur.list
```

> Note: The `--needed` option skips packages that are already installed.

To create a package list of your own, run the following commands.

```bash
pacman -Qqe > .pacman.list
```

```bash
yay -Qqe > .aur.list
``` -->
