# AngularProject

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.2.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Docker Development

You can also choose to start the application in a Docker environment. If you use the simple exapmle commands, the application will be runned by the names I use for the application.

### First (build Image)

First you will need to start with the command `docker build -t <ProjectName> . --platform=linux/amd64`
<!-- docker build -t client . --platform linux/amd64 -->
For example you can use `docker build -t client . --platform=linux/amd64`
This build the image of the application and tags it to a certain name `-t`.
The platform we are using here ` --platform=linux/amd64` is to make it possible to install linux package. We need this to install the google google-chrome-stable extension to test our application

### Second (Start Container)

Now you want to startup the development server by starting with `docker run -d -v ${PWD}:/app -v /app/node_modules -p 4201:4200 --name <ContainerName> --rm <projectName>`
For example you can use `docker run -d -v ${PWD}:/app -v /app/node_modules -p 4201:4200 --name team-trip-advisor-client --rm client`

### Third (Start Tests)

Before you can start the tests on SonarQube you need to start a local docker container for managing stuff. To start the local machine, you need to run `docker run -d --name sonarqube --platform linux/amd64 -p 9000:9000 sonarqube`.

To start the sonar tests execute `npm run sonar-scanner`/

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
