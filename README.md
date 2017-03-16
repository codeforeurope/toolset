# toolset for Linux -
```shell
sudo apt-get update
sudo apt-get install build-essential checkinstall libssl-dev
```
# Install NVM - for node
```shell
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash
```
## Check which version you can install 
```shell
 nvm ls-remote
 nvm install 7.7.2 #for example
```
## Make sure latest version of npm installed
```shell
 npm install npm@latest -g
```
# git 

## Install Git
```shell
 npm install git -g
```
## Install dotEnv for sensitive connection information saved in .env files
```shell
 npm install dotenv -g
```
## Install Standard for linting 
```shell
npm install standard -g 
```
### Run standard on your code - it can also be installed as an extension to code-insiders
```shell 
standard --fix 
```

# TODO
## Virtual Box img - with setup done
* All you need then is the image and Virtual box installed
 

# Code
NodeJS (advantages unit test, linting, security, enforced coding standards)
* Python
* JS
* R 


# Databases
* Mongo (for json / read data)
* Firebase (realtime)
* Postgres (for spatial data / higher performance)

# HTML
* Handlebars 
* SASS
* React
* Angular 
* Insert Favourite Framework here!



# IDE 
*Visual Studio Code Insiders
```shell
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64] http://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
sudo apt-get update
sudo apt-get install code-insiders
sudo update-alternatives --set editor /usr/bin/code-insiders
code-insiders . 
```
## Then to Open your project when in relevant directory



* brackets.io
* sublime
* insert favourite text editor here

# Debug
```shell
node --inspect --debug-brk filename.js
```

https://developer.chrome.com/devtools/docs/debugger-protocol
[https://code.visualstudio.com/blogs/2016/02/23/introducing-chrome-debugger-for-vs-code](Add chrome as external debugger)
https://chrome.google.com/webstore/detail/nim-node-inspector-manage/gnhhdgbaldcilmgcpfddgdbkhjohddkj
(NIM)
https://github.com/yury-s/v8-inspector

# Testing
Travis - https://travis-ci.org/ with travis.yml file defining the automatic test and deploy


# Translation i18n
## https://www.transifex.com/
```script 
sudo apt install transifex-client
```
### Login and register and copy setting to ~/.transifexrc
#### tx pull
#### tx push

# Communication
* Trello outdated - move to github
* use email
* slack bot 
* email address per project
