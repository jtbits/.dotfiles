# Dotfiles

## Steps to bootstrap on MAC
1) Install Apple's Command Line Tools
```sh
xcode-select --install
```
2) Clone repo into new hidden directory
```sh
git clone git@github.com:jtbits/.dotfiles.git ~/.dotfiles
```
3) Create symlinks in the Home directory to the real files in the repo
```sh
ln -s ~/.dotfiles/.zshrc ~/.zshrc
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```
4) Install Homebrew, followed by the software listed in the Brewfile
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
brew bundle --file ~/.dotfiles/Brewfile
cd ~/.dotfiles && brew bundle
```
