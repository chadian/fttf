<!-- $theme: default -->

# FastBoot to the Future
## Chad Carbert, @chadian on most things

---

# Before we talk FastBoot... 

---

- We are a Community ✌🏽
- opinionated holistic approach to common challenges
- RFCs, a healthy discussion and evolution
- diversified across organizations of all sizes, and types
- `ember-cli`, ember addons, and the big ecosystem
- Foundational growth: Ember Learning Team, EmberConf, meetups

---

# Be the Bark
![alt text](http://madhatted.com/images/2016-02-10/more-bark-projects.jpg)
* https://madhatted.com/2016/2/10/be-the-bark-ember-js-community (Matthew Beale, @mixonic, Ember Core)

---

# We are the bark
<img src="https://pbs.twimg.com/media/BgsvdC8CUAE6OuK.jpg" width=400px>

*the moment in which Alex realized the importance of bark*

- Ember Core Team Alumni & Mr. Router
- [The *very first* EmberConf 2014](https://www.youtube.com/watch?v=Syv_OTzHOr0)
- EmberConf DJ
- `ember-concurrency`
- FutureProof Retail
- Coming Soon: EmberConf 2017

---

# The web is a big, big world.
## and we're building ambitious applications
## Ember is the SDK for the web
- 🖥  `ember-electron`(see [Ghost Desktop](https://github.com/tryghost/Ghost-Desktop))
- 📱 `ember cordova`, `ember-cli-cordova`
- ⤴️ `ember-cli-deploy`
- **Stability without Stagnation**

---

# Currently in Ember
<img src="https://drive.google.com/uc?id=0B5cL_igoQlKrT2tpQzFMU0pxQjA" width="650">

---

# And then there's FastBoot!

## progressive enhancement for ambitious web apps.
###### (and more...)

---

<img src="https://drive.google.com/uc?id=0B5cL_igoQlKrQ05zWkJDeHI1bWs" width="700">

---

# The difference between
<img src="https://drive.google.com/uc?id=0B5cL_igoQlKra2JMcWhUdnE2cE0">

---

# And...
<img src="https://drive.google.com/uc?id=0B5cL_igoQlKrLWtrdEhUQktwLUE">

---


# Progressive Enhancement (the obvious win)

```sh
curl https://ember-fastboot.com
```
```html
  <body>
    
    <!-- EMBER RENDERED CONTENT! -->
    <div id="ember4704" class="ember-view"><div id="ember4719" class="ember-view liquid-container"><div id="ember4730" class="ember-view liquid-child"><div id="ember4735" class="ember-view main-hero"><div>

    ...
    
    <!-- the ember js payload -->
    <script src="https://fastboot-website-herokuapp-com.global.ssl.fastly.net/assets/vendor-7f3caf99c54521a2a6d4bd2969a9e9c1.js"></script>
    <script src="https://fastboot-website-herokuapp-com.global.ssl.fastly.net/assets/fastboot-website-983621bc95e9bdcc3780ea67e3950fd3.js"></script>

  </body>
```

---

# It's just an ember app
- check out `ember-fastboot.com` with the Ember Inspector *#bethebark*
- Your browser instantly shows **state**, html and css.
- The javascript payload *boots*, takes over (rips out initial render), and you're live

---

# At the core [`fastboot`](https://github.com/ember-fastboot/fastboot)

```js
const FastBoot = require('fastboot');

let app = new FastBoot({
  // `dist` is the result of your build
  // via `ember-cli`
  distPath: 'path/to/dist'
});

app.visit('/photos')
  .then(result => result.html());

```

## `ember app (at route) ➡️ rendered html`

https://github.com/ember-fastboot/fastboot

---

# get fastbooted 🤖
## [`ember-cli-fastboot`](https://github.com/ember-fastboot/ember-cli-fastboot)
## bootstrap your ember app

1. `ember install ember-cli-fastboot`
2. `ember build`
3. check your `dist`
4. `package.json`!

### builds become special, your app becomes fastbooted
###### build via `ember-cli`, #bethebark

---

# [`fastboot-app-server`](https://github.com/ember-fastboot/fastboot-app-server)
##### `request ➡️ (before) ➡️  render ➡️ (after) ➡️ response`
- express + middleware
- first pass within your FastBoot runtime (~ node)
- throw stuff in the shoebox for later
- `FastBoot` magic global

---

# DIY App Server
## Express + [`fastboot-express-middleware`](fastboot-express-middleware)

---

# Remember the route
## `/posts/:post_slug?includeMagic=true`

- Captures state
  - Matches on ember-app
  - Matches on express request
  - Matches on FastBoot `app.visit`

... *getting the router right*
*#bethebark*

---

# Tips and gotchas 💡🙈

- `ember fastboot --serve-assets`, *basic fastboot app server*
- Avoid `jQuery` and relying on `DOM` manipulation as much as possible
  - mind the hooks 🎣: `init`, `didReceiveAttrs`, `didUpdateAttrs`, `willRender` and `willUpdate`
- Your initial UI feels "ready", it isn't
  - consider disabled states on elements, and temporary indicators
- `FastBoot` vs `fastboot: Ember.service.inject()`
  - wrap `FastBoot`with `fastboot.get('isFastboot')`

---

# Tips and gotchas 💡🙈
- Forget "ajax". Use `ember-network`, `fetch` spec and it's "isomorphic"
- Whitelist node modules in `package.json`
- Clean the build
```
if (!process.env.EMBER_CLI_FASTBOOT) {}
```

---

# What else can we do on this request/response trip through nodeland?
## Think about
- **state**
- **presentation** of state
- **consumers** of state
- **process** by which state is consumed
- *available resources*

---

# Case study: e-mail 💌
<img src="https://drive.google.com/uc?id=0B5cL_igoQlKrendXZ3BqRmJIMGM" width="800">

---

# Case study: e-mail 💌
- email is **text** + **html** *+ css*
- ember does both *and builds css*
- ## hello fastboot

---

# Case study: e-mail 💌
- 🔌  power of existing components (`ember-i18n`)
- 🔌 power of existing addons
- 🚜 configuration via node `process.env`
  - bring in your API keys and secrets
- 🛠 build fast and on the fly 👐🏽 *via ember serve*
- email = no external stylesheets
- `express` middleware is your 🏭 assembly line
- ❤️ the route

- `ember`➡️ `ember-cli-fastboot` ➡️ `express.use` middleware response ➡️ `cheerio` + `juice` ➡️ `mailgun`

---

# Case study: playing with fire 😈🔥

> ... the point of running your client-side JavaScript application on the server is not to replace your existing API server.

> Tom Dale, [You're Missing the Point of Server-Side Rendered JavaScript Apps](http://tomdale.net/2015/02/youre-missing-the-point-of-server-side-rendered-javascript-apps/)
   
.  
.
.

... or don't muddy the waters  

---

# Case study: playing with fire 😈🔥
>*if the 👠 fits, 💃🏻*
> \- @chadian

---

# Dear Diary 😈🔥
1. Prototype it -- *(`ember-cli`, `ember-bootstrap`)*
2. Oh, that API -- *github profile picture with `ember-network`*
3. Existing data -- *pull it in (mongo via npm and shoebox)*
4. Make it pretty -- `ember-moment` and `ember-remarkable`
5. Paginate it -- `ember-cli-pagination`
6. I want to add posts -- *`post` via `express` middleware`
8. ... profit 💸
7. ... move existing data to express middleware and build out API?
8. ... more profit 💸💰💵

## consider the alternative

---

# Bonus Tips

- you're in nodeland, go nuts
- Environment variables at FastBoot runtime
```js
if (fastboot.get('isFastBoot')) {
  Ember.get(FastBoot.require('process'), 'env.ENVIRONMENT_VARIABLE')
}
```
- `deferRendering(thenable)`
- `nodemon` in your express app, watch your dist 
  - `ember s`, `ember fastboot`, `nodemon server.js -w . ../dist`
- Node debug or `node --inspect --debug-brk` (natively in Chrome with `node >= v6.3.0`)

---

# other ideas
- static embeddable
  - simple html deliverable *(ie: messaging, )*
  - ember app to compose
    - same api
    - same ember components
    - fastboot renders and delivers
- hardware + other npm sources
  - don't require API wrappers necessarily
  - useful visual resources and feedback
- e-commerce
  - speed is key, take my money
- static sites / cms
- base64 inline images (and store in shoebox), wrap with service

---

# the future
- rehydration (we paid for that)
- ❓❓ spitballing here, fastboot templates ❓❓
- `POST`? [Ideas are being tossed around](https://github.com/emberjs/rfcs/pull/185) 
- ... and other cool stuff, come hang out in `-fastboot` on the ember slack

---

# 👨🏽‍💻 dream big and #bethebark 🐶🌲
## Thank you

---
