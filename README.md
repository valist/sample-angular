# Valist Angular sample

This example demonstrates how to set up a configuration for an Angular application but can work with many other applications built with Node.js as well with slight modification.

As Angular does not require any custom server to run, the "static" configuration is used. After the build is finished, the content of "/app/dist/example-app/" will be hosted by a  web server for static website hosting. 

### valist.yml
```yaml
services:
  runtime: static
  dockerfile: valist.Dockerfile
  dist: /app/dist/example_app
  cmd: node_modules/.bin/ng build --prod
```  


### valist.Dockerfile
```
FROM node:alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
```

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
# sample-angular
