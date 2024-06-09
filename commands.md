# Useful commands

```bash
# In WSL2, install go 1.22.2
wget https://go.dev/dl/go1.22.2.linux-amd64.tar.gz
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.22.2.linux-amd64.tar.gz
vim ~/.bashrc
export PATH=$PATH:/usr/local/go/bin
source ~/.bashrc
go version
```


```bash
# In WSL2, install nodejs npm and sass
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt install nodejs npm
sudo npm install -g sass
node -v
npm -v
sass -v
```

```bash
wget https://github.com/gohugoio/hugo/releases/download/v0.125.4/hugo_extended_0.125.4_linux-amd64.deb
sudo dpkg -i hugo_extended_0.125.4_linux-amd64.deb
hugo version
```

```bash
# Uninstall hugo
sudo apt-get remove hugo
```

```bash
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```

```bash
hugo new site presentation_website
cd presentation_website
git init
git submodule add https://github.com/luizdepra/hugo-coder themes/coder
# Two submodules, in case I want to change the theme
git submodule add https://github.com/rhazdon/hugo-theme-hello-friend-ng themes/ng
echo 'theme = "coder"' >> config.toml
hugo new posts/my-first-post.md
hugo server -D
```
