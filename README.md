# toolset for Ubuntu

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
 sudo apt install git
```
## set up git 

```shell 
git config --user.username x@x.com
git config --user.password
```
Recommend setting up ssh as it will save a lot of time for you typing passwords and encrypts your traffic
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

```shell 
ssh-keygen -t rsa -b 4096 -C "x@x.com"
##  put in passphrase for cert
## assuming you save to default filename - you can change below if you pick different file name
## add to agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

Then add to your github profile 
https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/

```shell
sudo apt-get install xclip
# Downloads and installs xclip. If you don't have `apt-get`, you might need to use another installer (like `yum`)

xclip -sel clip < ~/.ssh/id_rsa.pub
# Copies the contents of the id_rsa.pub file to your clipboard
```
Add under your ssh key on your github profile


## Install dotEnv for sensitive connection information saved in .env files

```shell
 npm install dotenv-safe --save 
```
In your JS files you can include API tokens by 
```javascript
require('dotenv-safe').load({
  allowEmptyValues: true,
  sample: 'sample.env'
})
```
where your tokens are in a .env file in the root of the project and sample.env is also in root of the project and contains the variables you expect to use

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
## For settings 

```command 
ctrl-shift-p settings
# select user settings 
```
Example user Setting or per workspace settings

```json
{
  "telemetry.enableCrashReporter": false,
  "telemetry.enableTelemetry": false,
  "prettier.tabWidth": 2,
  "editor.tabSize": 2,
  "editor.detectIndentation": false
}
```
## For Extensions to see what you have installed

```command
ctrl-shift-x ext @installed 
```
![Extensions Installed Picture](code-insiders-extensions.png)

for debuging in code-insiders copy this into .vscode/launch.json where 3000 is your port and you are debugging on localhost
[tasks.json](https://raw.githubusercontent.com/skolmer/react-hot-boilerplate-vscode/master/.vscode/tasks.json)
```json
{
    // Use IntelliSense to learn about possible Node.js debug attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
    {
             "name": "Debug",
                "type": "chrome",
                "request": "launch",
                "webRoot": "${workspaceRoot}",
                "url": "http://localhost:3000", 
                "userDataDir": "${workspaceRoot}/.vscode/chrome",
                "sourceMaps": true,
                "preLaunchTask": "development",
                "smartStep": true,
                "internalConsoleOptions": "openOnSessionStart",
                "skipFiles": [
                    "${workspaceRoot}/node_modules/**/*.js",
                    "${workspaceRoot}/lib/**/*.js"
                ],
    "sourceMapPathOverrides": {
        "/source/*": "${workspaceRoot}/*",
        "webpack:///./*":   "${webRoot}/*",                    // Example: "webpack:///./src/app.js" -> "/users/me/project/src/app.js",
        "webpack:///./~/*": "${workspaceRoot}/node_modules/*", // Example: "webpack:///./~/querystring/index.js" -> "/Users/me/project/node_modules/querystring/index.js"
        "webpack:///*":     "*",                               // Example: "webpack:///C:/project/app.ts" -> "C:/project/app.ts"
        "meteor://💻app/*": "${webRoot}/*"                    // Example: "meteor://💻app/main.ts" -> "c:/code/main.ts"
    }   
    }
    ]
}

```


## Then to Open your project when in relevant directory

```shell 
code-insiders .
```
For other code-insiders resources

https://github.com/viatsko/awesome-vscode 

Other ide include
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

# React 

## Preact / Inferno can be accomodated 

If using react can follow the following guideline to get running quickly

https://react-server.io/docs
```script
npm install --save react react-dom


# install yeoman
npm install -g yo

# install the react-server generator
npm install -g generator-react-server

# make a new react-server project in the CURRENT directory
yo react-server

# run the new app
npm run start

# go to http://localhost:3000
```
Other tools for React include lighthouse (performance debugging in browser extension), rch, react-monocle (component hirearchy) , rg (redux generate)
```shell
npm i -g lighthouse redux-generators react-component-hierarchy react-monocle react-quick-templates
rqt --help
```

## useful tool

```shell

npm i -g html-to-react-components
html2react index.html -c es5 -m es6 -e js -o ./components
```

# Style 

## To convert existing style to react use

http://staxmanade.com/CssToReact/


# Caching ServiceWorker and Performance analysis

# Packing resource files 

```shell
npm install -g webpack

npm install -D babel-core babel-loader babel-preset-es2015 babel-preset-react babel-preset-stage-0



```
Add .babelrc and webpack.config.js file to project

## Alternative to webpack

Rollup - not webpack 
```shell
npm install -g rollup
```

## Fonts 

Woff2 
https://github.com/CrocoDillon/font-store

http://bdadam.com/blog/loading-webfonts-with-high-performance.html



# Mongodb

https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/
```shell
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

echo "deb [ arch=amd64,arm64 ] http://repo.mongodb.org/apt/ubuntu yakkety/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list

sudo apt-get install -y mongodb-org

sudo service mongod start

```

# Other References 

Other toolset / setup pages 
[Ory] (https://github.com/ory/workshop-dbg)
Code coverage
[Nyc](https://github.com/istanbuljs/nyc)

# Testing 

[Protractor] 


# JSON HTTP endpoints 

[httpie](https://github.com/jakubroztocil/httpie)


# [Curated](Curated.md)
# [Docker](Docker.md)
# [Env](Env.md)
# [Production Setup](ProductionSetup.md)
# [Workshops](Workshops.md)