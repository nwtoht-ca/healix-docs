# Website

This website is built using [Docusaurus 2](https://docusaurus.io/), a modern static website generator.

### Environment Set Up

* Install nvm and npm (https://www.freecodecamp.org/news/node-version-manager-nvm-install-guide/)
  * NB This requires XCode CLI tools to be installed. Non-devs, go to https://nodejs.org/en/download/, download and launch the installer for your computer  
* Install git (might be on Mac already)
* Install Visual Studio Code
* Must have a github account and SSH key
* Pull the source code:

```
git clone git@github.com:nwtoht-ca/healix-docs.git
```

* Set up your local development branch (in Visual Studio, create a branch name <yourname>dev or something)

### Installation

```
cd ./healix-docs.git # Whereever you installed it
git clone git@github.com:nwtoht-ca/healix
$ npm i
```

### Local Development

```
$ npm start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

### Build

```
$ npm build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

