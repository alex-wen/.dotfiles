# .dotfiles

WIP

## alacritty
### installation
taken from `https://gist.github.com/Aaronmacaron/8a4e82ed0033290cb2e12d9df4e77efe`
```
# Install required tools
sudo apt-get install -y cmake libfreetype6-dev libfontconfig1-dev xclip
sudo apt install cargo

# Download, compile and install Alacritty
git clone https://github.com/jwilm/alacritty
cd alacritty
cargo install

# Add Man-Page entries
sudo mkdir -p /usr/local/share/man/man1
gzip -c alacritty.man | sudo tee /usr/local/share/man/man1/alacritty.1.gz > /dev/null

# Add shell completion for bash and zsh
mkdir -p ~/.bash_completion
cp alacritty-completions.bash ~/.bash_completion/alacritty
echo "source ~/.bash_completion/alacritty" >> ~/.bashrc

sudo cp alacritty-completions.zsh /usr/share/zsh/functions/Completion/X/_alacritty

# Create desktop file
cp Alacritty.desktop ~/.local/share/applications/

# Copy binary to path
sudo cp target/release/alacritty /usr/local/bin

# Use Alacritty as default terminal (Ctrl + Alt + T)
gsettings set org.gnome.desktop.default-applications.terminal exec 'alacritty'

# Remove temporary dir
cd ..
rm -r alacritty
```

### configuration
```
ln -s ~/.dotfiles/alacritty/alacritty.yml ~/.alacritty.yml
```

## i3
```
ln -s ~/.dotfiles/i3/i3blocks.conf ~/.config/i3/i3blocks.conf
ln -s ~/.dotfiles/i3/config ~/.config/i3/config
```

## vim
```
ln -s ~/.dotfiles/vim/vimrc ~/.vimrc
ln -s ~/.dotfiles/vim/autoload ~/.vim/autoload
ln -s ~/.dotfiles/vim/colors ~/.vim/colors
```

## zsh
```
ln -s ~/.dotfiles/zsh/zshrc ~/.zshrc
```

## tmux
```
ln -s ~/.dotfiles/tmux/tmux.conf ~/.tmux.conf
```

## git
```
ln -s ~/.dotfiles/git/gitconfig ~/.gitconfig
```
