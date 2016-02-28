### Quick links
- [Demo](#demo)
- [Angular 2](#angular-2)
- [Installation](#installation)
    - [NPM](#install-with-npm)
    - [Bower](#install-with-bower)
    - [NuGet](#install-with-nuget)
    - [Custom](#custom-build)
    - [Manual](#manual-download)
- [Webpack](#webpack)
- [Support](#support)
    - [FAQ](#faq)
    - [Code of Conduct](#code-of-conduct)
    - [PREFIX MIGRATION GUIDE](#prefix-migration-guide)
    - [Supported browsers](#supported-browsers)
    - [Need help?](#need-help)
    - [Found a bug?](#found-a-bug)
- [Contributing to the project](#contributing-to-the-project)
- [Development, meeting minutes, roadmap and more.](#development-meeting-minutes-roadmap-and-more)


# Demo

Do you want to see directives in action? Visit http://angular-ui.github.io/bootstrap/!

# Angular 2

Are you interested in Angular 2? We are on our way! Check out [ng-bootstrap](https://github.com/ui-bootstrap/core). 

# Installation

Installation is easy as UI Bootstrap has minimal dependencies - only the AngularJS and Twitter Bootstrap's CSS are required.
*Notes:* 
* Since version 0.13.0, UI Bootstrap depends on [ngAnimate](https://docs.angularjs.org/api/ngAnimate) for transitions and animations, such as the accordion, carousel, etc. Include `ngAnimate` in the module dependencies for your app in order to enable animation.
* UI Bootstrap depends on [ngTouch](https://docs.angularjs.org/api/ngTouch) for swipe actions. Include `ngTouch` in the module dependencies for your app in order to enable swiping.

## Angular Requirements
* UI Bootstrap 1.0 and higher _requires_ Angular 1.4.x or higher and it has been tested with Angular 1.4.8.
* UI Bootstrap 0.14.3 is the _last_ version that supports Angular 1.3.x.
* UI Bootstrap 0.12.0 is the _last_ version that supports Angular 1.2.x.

## Bootstrap Requirements
* UI Bootstrap requires Bootstrap CSS version 3.x or higher and it has been tested with Bootstrap CSS 3.3.6.
* UI Bootstrap 0.8 is the _last_ version that supports Bootstrap CSS 2.3.x.

#### Install with NPM

```sh
$ npm install angular-ui-bootstrap
```

This will install AngularJS and Bootstrap NPM packages.

#### Install with Bower
```sh
$ bower install angular-bootstrap
```

Note: do not install 'angular-ui-bootstrap'.  A separate repository - [bootstrap-bower](https://github.com/angular-ui/bootstrap-bower) - hosts the compiled javascript file and bower.json.

#### Install with NuGet
To install AngularJS UI Bootstrap, run the following command in the Package Manager Console

```sh
PM> Install-Package Angular.UI.Bootstrap
```

#### Custom build

Head over to http://angular-ui.github.io/bootstrap/ and hit the *Custom build* button to create your own custom UI Bootstrap build, just the way you like it.

#### Manual download

After downloading dependencies (or better yet, referencing them from your favorite CDN) you need to download build version of this project. All the files and their purposes are described here:
https://github.com/angular-ui/bootstrap/tree/gh-pages#build-files
Don't worry, if you are not sure which file to take, opt for `ui-bootstrap-tpls-[version].min.js`.

### Adding dependency to your project
