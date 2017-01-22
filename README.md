# FastBoot to the Future ⚡️
Taking a look at what's possible with [Ember FastBoot](ember-fastboot.com).

## Contribute
Have an example app? Open a PR! It would be great to see how others are using Ember FastBoot.

## Resources
- [Ember FastBoot website](https://ember-fastboot.com)
- [Introduction to Ember FastBoot (Global Ember Meetup)](https://vimeo.com/157688134)
- [You’re Missing the Point of Server-Side Rendered JavaScript Apps](http://tomdale.net/2015/02/youre-missing-the-point-of-server-side-rendered-javascript-apps/)
- [My Ember PDX Meet Up Slides](https://github.com/chadian/fttf/blob/master/ember-portland-meetup-notes.md)

## FastBoot example apps
* [Email Rendering, chadian/fttf-email-example](https://github.com/chadian/fttf-email-example)
  * `FastBoot.require` and whitelisted `package.json`
  * Using `fastboot` service properties
     * `isFastBoot`
     * `response`
  * `ENV` variables at FastBoot runtime via `Fastboot.require('process').env`
  * `fastboot-app-server`
  * response interceptor middleware to inline css, dispatch
* [Duct taped Blog, chadian/fttf-dear-diary](https://github.com/chadian/fttf-dear-diary)
  * `FastBoot.require` and whitelisted `package.json`
  * Using `fastboot` service properties
     * `isFastBoot` 
     * `shoebox`
  * `mongodb` in `model` hook via `FastBoot.require('mongodb')`
  * `express` with `fastboot-express-middleware`
  * Shared express server with API middleware