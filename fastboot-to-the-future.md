<!-- $theme: default -->

# FastBoot to the Future
## Chad Carbert, @chadian  on most things

---

# Before we get started... 
## Ember is a story of ❤️

---

- We are a Community ✌🏽
- unified, holistic approach to common challenges
- RFCs, a healthy discussion and evolution
- diversified across organizations of all sizes, and types
- `ember-cli`, ember addons, and the big ecosystem
- We're growing: Ember Learning Team, EmberConf, meetups

---

# Be the Bark
![alt text](http://madhatted.com/images/2016-02-10/more-bark-projects.jpg)
* https://madhatted.com/2016/2/10/be-the-bark-ember-js-community (Matthew Beale, @mixonic)

---

# We are the bark
<img src="https://pbs.twimg.com/media/BgsvdC8CUAE6OuK.jpg" width=400px>

*the moment in which Alex realized 'be the bark'*

- Ember Core Team Alumni & Mr. Router
- [The *very first* EmberConf 2014](https://www.youtube.com/watch?v=Syv_OTzHOr0)
- EmberConf DJ
- `ember-concurrency`
- FutureProof Retail
- EmberConf 2017

---

# The web is a big, big world.
## ambitious applications
## Ember is the SDK for the web
- 📱  `ember-electron`(see [Ghost Desktop](https://github.com/tryghost/Ghost-Desktop))
- 🖥 `ember cordova`, `ember-cli-cordova`
- ⤴️ `ember-cli-deploy`
- **Stability without Stagnation**

---

# And FastBoot!

## progressive enhancement for ambitious web apps.
###### (and more...)

---

# Progressive Enhancement
## The obvious win

```sh
curl https://ember-fastboot.com
```
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Ember FastBoot</title>
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width">
  ...
  </head>
  <body>
    ...
    <script src="https://fastboot-website-herokuapp-com.global.ssl.fastly.net/assets/vendor-7f3caf99c54521a2a6d4bd2969a9e9c1.js"></script>
    <script src="https://fastboot-website-herokuapp-com.global.ssl.fastly.net/assets/fastboot-website-983621bc95e9bdcc3780ea67e3950fd3.js"></script>
   ...
  </body>
</html>
```

---

# The difference between
<img src="https://drive.google.com/uc?id=0B5cL_igoQlKra2JMcWhUdnE2cE0">

---

# And...
<img src="https://drive.google.com/uc?id=0B5cL_igoQlKrLWtrdEhUQktwLUE">

---

# It's just an ember app
- check out `ember-fastboot.com` with the Ember Inspector (be the bark!)
- Your browser instantly shows **state**, it's html and css.
- The javascript payload *boots*, takes over (rips out that initial render), and you're live

---

# Ember


---

# Ember with FastBoot


---

# At it's core

```
const FastBoot = require('fastboot');

let app = new FastBoot({
  distPath: 'path/to/dist'
});

app.visit('/photos')
  .then(result => result.html());

```

## `ember app (at route) ➡️ rendered html`

https://github.com/ember-fastboot/fastboot

... *getting the router right*

---

# get your build fastbooted 🤖
## `ember-cli-fastboot`
## bootstrap your ember app

1. `ember install ember-cli-fastboot`
2. `ember build`
3. check your `dist`
4. `package.json`!

### builds are special, your app becomes fastbooted âĄď¸

---

# FastBoot App Server
##### `request ➡️ (before) ➡️  render ➡️ (after) ➡️ response`
- express + middleware
- first pass within your FastBoot runtime (~ node)
- throw stuff in the shoebox for later
- `FastBoot` magic global

---

# Tips and gotchas 💡🙈

- `ember fastboot --serve-assets` *
- Avoid `jQuery` and relying on `DOM`manipulation as much as possible
- Use `ember-network`, `fetch` spec and just works.
- whitelist node modules in package.json
- __TODO__ hooks???

---

# What else can we do along the way?
## Think about
- **state**
- **consumers** of state
- **process** by which state is consumed
- *available resources*

---

# Case study: non-browser consumer 💌

---

# Case study: playing with fire 😈🔥

> ... the point of running your client-side JavaScript application on the server is not to replace your existing API server.

> Tom Dale, [You're Missing the Point of Server-Side Rendered JavaScript Apps](http://tomdale.net/2015/02/youre-missing-the-point-of-server-side-rendered-javascript-apps/)
   
.  
.
.

... or don't muddy the waters  

---

# Case study: playing with fire đĽđ
## if the đ fits, dance. - @chadian

---

#
#
#

---

# Bonus Tips

- Environment variables at FastBoot runtime
```js
if (fastboot.get('isFastBoot')) {
	Ember.get(FastBoot.require('process'), 'env.FTTF_GITHUB_URL')
}
```
- Node debug or `node --inspect --debug-brk` (natively in Chrome with `node >= v6.3.0`)

---

# 👨🏽‍💻 dream and #bethebark
## Thank you

---
