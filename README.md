# MicroFrontends

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.2.0.

This is a POC for micro frontends hosted in a monorepo.

## Development server

Run `npm run run:all` for a dev server. Navigate to `http://localhost:5000/`. The app will automatically reload if you change any of the source files. This command runs the shell app as well as all defined child apps.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

Adding a new MFE involves adding a new app to the project using the `@angular-architects/module-federation` schematic, then editing its and the shell's `webpack.config.js`. In the child app's `webpack.config.js`, you will need to add the root module to its exposures. For the shell's, you will need to add the new app as a remote.

Summary:
1. `ng add @angular-architects/module-federation --project <project name> --port <port>`
2. Edit the new project's `webpack.config.js` to expose its root module and add it to the shell's `webpack.config.js` remotes.
3. Add routes to the shell's routing module to make the MFE accessible from the shell app
4. Update the shared array as well if necessary

See the existing `wepback.config.js` files in the shell and existing MFEs for examples.


## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
