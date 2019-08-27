# wizard

See also the related API spec: https://github.com/intermine/wizard-api-specs/

---

## To run

### Requirements
- git
- Node and npm (ideally installed via [nvm](https://github.com/nvm-sh/nvm))
- The [InterMine Compose server](https://github.com/intermine/intermine_compose).


### Clone and start the wizard

```bash
git clone git@github.com:intermine/wizard.git
cd wizard
npm install
npm start
```

Visit [localhost:3000](http://localhost:3000) to see the wizard, or [localhost:3000/dev](http://localhost:3000/dev) for quick links to all the wizard pages

### Developing

If you're developing and would like the server to auto-restart after you've changed a server-side js file, run this instead of npm start

```bash
npx nodemon bin/www
```

#### Building the wizard

Webpack glues all of the disparate js files into a single built js in the dist folder.

Build once:  

```
  npm run build
```

Build, and refresh when changes are made:

```
npm run devBuild

```

|task|command|
|----|-------|
|build js| `npm run build`|
|dev: rebuild and refresh server when changes are made|`npm run dev`|
|dev: refresh server which files are changed|`npm run refreshServer`|
|dev: rebuild on js filechange|`npm run watchBuild`|
### Running on a different port

Dev:

```bash
PORT=SOMEPORT npx nodemon bin/www
```

Prod:

```bash
PORT=SOMEPORT npm start
```

## Docker

### Build docker image

```bash
docker build -f Dockerfile -t intermine/wizard:latest .
```

### Run wizard in a docker container

```bash
docker run --rm -p 9992:8080 intermine/wizard:latest 
```
You can visit wizard at `localhost:9992`

### Docker Compose

Start wizard with all other InterMine Cloud components using docker compose.

```bash
docker-compose up --build --force-recreate
```
You can visit wizard at `localhost:9992`