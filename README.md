# Docusaurus Project - PSG2

This is the Docusaurus project by **Samuel Tamayo Balogh** for PSG2.  
The project is deployed using GitHub Pages and GitHub Actions.

You can view it at the following link:  
[https://samtbalogh.github.io/PSG2Docusaurus](https://samtbalogh.github.io/PSG2Docusaurus)

# Website

This website is built using [Docusaurus](https://docusaurus.io/), a modern static website generator.

### Installation

```
$ yarn
```

### Local Development

```
$ yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

### Build

```
$ yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

### Deployment

Using SSH:

```
$ USE_SSH=true yarn deploy
```

Not using SSH:

```
$ GIT_USER=<Your GitHub username> yarn deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.
