# install libs
```
sudo apt-get install libncurses5-dev libgnome2-dev libgnomeui-dev \
    libgtk2.0-dev libatk1.0-dev libbonoboui2-dev \
    libcairo2-dev libx11-dev libxpm-dev libxt-dev python-dev \
    python3-dev ruby-dev liblua5.1 lua5.1-dev libperl-dev git
```
# download vim source code
```
git clone https://github.com/vim/vim.git
```

# remove system pre-installed vim
```
dpkg -l | grep vim
sudo apt-get remove vim vim-runtime vim-common vim-tiny
```

# config with python
```
./configure --with-features=huge \
            --enable-multibyte \
            --enable-rubyinterp=yes \
            --enable-pythoninterp=yes \
            --with-python-config-dir=/usr/lib/python2.7/config \
            --enable-perlinterp=yes \
            --enable-luainterp=yes \
            --enable-gui=gtk2 --enable-cscope --prefix=/usr
```
# make
```
make VIMRUNTIMEDIR=/usr/share/vim/vim80
```

# vimrc
```
cd ~

git clone git://github.com/haochengz/vimrc.git ~/.vim

ln -s ~/.vim/vimrc ~/.vimrc

git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim

vim +PluginInstall +qall
```
