### Javascript Decorators for Angular 1.x

Writing Angular 1.x apps with ES6? Tired of declaring classes, adding manual injections, and registering everything with your angular modules? Fear not!

Works with babelJS and theoretically Typescript 1.5+ (coming soon!)

Does not work with Traceur (currently) as it does not support decorators (just annotations).

See [Javscript Decorator Spec](https://github.com/wycats/javascript-decorators) from more info. 

Work In Progress! Input / Pull Requests welcome!

```js
import {ngInject, ngController, ngService, ngModule} from 'angular-decorate';

@ngModule({
  name: 'demoApp',
  dependencies: [],
  inject: ['$http'],
  configure: ['$httpProvider']
})
export class DemoApp {
  static run(http){
    console.log('run',http);
  }
  static config(httpProvider){
    console.log('config',httpProvider);
  }
}

@ngController({
  module: 'demoApp',
  name: 'DemoController',
  inject: ['$http']
})
export class DemoController {
  constructor(http){
    this.http = http;
  }
}

@ngService({
  module: 'demoApp',
  name: 'DemoService',
  inject: ['$http']
})
export class DemoService {
  constructor(http){
    this.http = http;
  }
}

```