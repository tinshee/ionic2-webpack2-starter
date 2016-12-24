# Ionic 2 Webpack Starter

Ionic 2 starter project using Webpack 2 and [@ngtools/webpack](https://github.com/angular/angular-cli/tree/master/packages/webpack) for AoT template compilation.

Includes Sass support for [theming your app](https://ionicframework.com/docs/v2/theming/theming-your-app/). Styles can be encapsulated in the component, without the need for a `selector` metadata property like in projects generated with the Ionic CLI.

```typescript
@Component({
  templateUrl: 'home.page.html',
  styleUrls: ['home.page.scss']
})
export class HomePage { }
```

## Usage

### Clone This Project

Simply clone this project and use it as it is, or rename it to whatever you like.
```
git clone https://github.com/mirkonasato/ionic2-webpack2-starter my-app
```

### Install Dependencies

Install all the dependencies (this only needs to be done once) with NPM:
```
cd my-app
npm install
```
(You can also use [Yarn](https://yarnpkg.com/) instead of NPM of course.)

### Add Cordova

If you only want to create a (progressive) web app you can skip this step. To be able to build a mobile app with Cordova, create a new Cordova project in a `cordova` sub-folder using the [Cordova CLI](https://cordova.apache.org/docs/en/latest/guide/cli/) (did I say Cordova enough times?):

```
cordova create cordova
```

then edit `cordova/config.xml` and set your app id, name, etc.

### Local Development Server

To start a local development web server with automatic refresh type:
```
npm run serve
```
Your application will be accessible at [localhost:8080](http://localhost:8080/) by default. See the [webpack-dev-server docs](https://webpack.github.io/docs/webpack-dev-server.html) if you want to customise anything.

### Build Targets

* `npm run build`: builds the project as a (progressive) web app inside the `dist` folder.
* `npm run build:prod`: same as above but with production settings, i.e. it enables Angular production mode, Ahead-of-Time template compilation, and code obfuscation/minification.
* `npm run build:cordova`: prepares the project for building a mobile app with Cordova. The output in this case is the `cordova/www` folder.
* `npm run build:cordova:prod`: same as above but with production settings.

### Running as a Mobile App

Simply build the project as described above, then use [Cordova CLI](https://cordova.apache.org/docs/en/latest/guide/cli/) from inside the `cordova` sub-folder to build and run.

E.g. for Android build the project in the top-level folder
```
npm run build:cordova
```
add Android as a platform (only needs to be done once):
```
cd cordova
cordova platform add android
```
and then you run the app in an emulator with
```
cordova run android --emulator
```

For iOS it's the same, just replace `android` with `ios`. Please refer to the [Cordova CLI docs](https://cordova.apache.org/docs/en/latest/guide/cli/) for the full list of available commands.
