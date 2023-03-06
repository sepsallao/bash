# NPM, NVM and Node ISSUE

## Install NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash

## Check Version
nvm --version

###### Do O need this?
source ~/.bashrc 
nvm ls-remote

## Install version NVM
nvm install <version>
nvm install 16.0.0

## To use:
nvm install <version>
nvm use 16.0.0

## Test with console.log
node -e "console.log('running nodejs' + process.version)"

## Install node with NVM 
nvm install node

## Update NPM
npm cache clean -f 
npm install -g npm

## To create Node Modules
npm install

or
npm install --legacy-peer-deps