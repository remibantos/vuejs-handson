---

# VueJS By The @vue/cli

https://gitpitch.com/remibantos/vuejs-handson

---

![Alt](https://i.imgflip.com/2dyfd5.jpg "Thinking cat")

---

### What is VueJS ?
<!-- .slide: style="text-align: left;"> -->
@size[0.7em](*"Vue, pronounced /vjuː/ like view, is a progressive framework for building user interfaces.<br/>Unlike other monolithic frameworks, Vue is designed from the ground up to be incrementally adoptable.<br/>The core library is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects.<br/>Vue is also perfectly capable of powering sophisticated Single-Page Applications when used in combination with modern tooling and supporting libraries."*)

---

### History
@div[left-50]
![Alt](https://pbs.twimg.com/profile_images/888432310504370176/mhoGA4uj_400x400.jpg "Evan You")
@divend
@div[right-50]
@size[0.8em](In February 2014, Evan You publish the first VueJS version)
<br/>
@size[0.7em](*"I figured, what if I could just extract the part that I really liked about Angular and build something really lightweight without all the extra concepts involved?”*)
@divend

---

### In a few words...

---?image=https://d.ibtimes.co.uk/en/full/1473536/john-mcafee-dark-web-hack-grandma.jpg&size=contain

### @color[white](Accessible)


---

* Easy learning curve. 
* An app can be built in a few minutes: [JSFiddle - "TODO List" Sample app](https://jsfiddle.net/Lsgc2rhr/9/?utm_source=website&utm_medium=embed&utm_campaign=Lsgc2rhr)

---?image=http://a406.idata.over-blog.com/600x398/1/57/40/12/Arts-Photo-Tableau/afp.jpg&size=contain

### @color[white](Versatile)

---

VueJS can be used for many different needs, in many different ways, you can create a small widget, a Single Page Application, components, 
complex apps with routing, state management, ...
<br/>
You can create templates in DOM, inline templates, or package them in a .vue component.

---?image=https://i3.cpcache.com/product/419243731/Warp_Speed_Dark_T-Shirt_300x300.jpg&size=contain

### @color[yellow](Performant)

---

* VueJS, like other modern framework use virtual dom where the DOM can be represented as a data structure in Javascript
* Good position in JS frameworks benchmarks
* Links:
  * [https://www.stefankrause.net/wp/?p=45]
  * [https://vuejs.org/v2/guide/comparison.html]
  * [https://medium.com/js-dojo/whats-the-deal-with-vue-s-virtual-dom-3ed4fc0dbb20]

---

# Lets code !

---
### Prerequistes

npm: https://www.npmjs.com/get-npm

---

### @vue/cli
* Interactive project scaffolding via @vue/cli
* Zero config rapid prototyping via @vue/cli + @vue/cli-service-global
* A runtime dependency (@vue/cli-service) that is:
    * Upgradeable
    * Built on top of webpack, with sensible defaults
    * Configurable via in-project config file
* A rich collection of official plugins integrating the best tools in the frontend ecosystem
* A full graphical user interface to create and manage Vue.js projects

---
### Install vue-cli

```bash
npm install -g @vue/cli
```

---

### Hello World !

```bash
vue create swapui
cd swapui
```

Select the default and click enter

---

### Idea settings

![Alt](assets/idea1.jpg?size=container "idea1")

---

![Alt](assets/idea2.jpg?size=container "idea1*2")

---

![Alt](assets/idea3.jpg?size=container "idea1*2")

---

### What do we have here...

---
### VueJS components

* template = HTML component template

```javascript
const MyDate = {
    template: '<h1>My date</h1>'
}
```
</div>

---
### VueJS components

* template = HTML component template
* data = internal components attributes

```javascript
const MyDate = {
    template: '<h1>{{date}}</h1>',
    data() {
        return {
            date: new Date()
        }
    }
}
```
---
### VueJS components

* template = HTML component template
* data = internal components attributes
* methods = components functions

```javascript
const MyDate = {
    template: '<h1>{{date}}</h1> {{hello()}} {{date}}',
    data() {return {date: new Date()}},
    methods : {
        hello() {
            return 'hello world';
        }
    }
}
```

---
### VueJS components
* template = HTML component template
* data = internal components attributes
* methods = components functions
* props = component parameters

```javascript
const MyDate = {
    props: ['name'],
    template: '<h1>{{date}}</h1> {{hello()}} {{date}}',
        data() {return {date: new Date()}},
    methods : {
        hello() {
            return 'hello ' + ${this.name};
        }
    }
}
```

---
### VueJS components

* template = HTML component template
* data = internal components attributes
* methods = components functions
* props = component parameters
* components = list components dependencies

```javascript
import MyDate  from './MyDate'
const MyComponent = {
    template: '<h1>Hello World <my-date/> </h1>',
    components : {MyDate}
}
```

---
### Single file component (.vue)
```html
<template>
    <div class="hello">
        {{message}}
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
        message: 'You loaded this page on ' + new Date().toLocaleString()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
```
---

### Web components foundation
<!-- .slide: style="text-align: left;"> -->
@size[0.6em](*"The Web Components / Custom Elements spec allows you to define your own custom elements in the browser and the logic attached to them. It’s been a long time coming, but it’s almost here. The advantage of Web Components is that they are interoperable between any framework or library, or even Vanilla JS. Thanks to Vue’s small size, with the help of a plugin, you can create native custom elements from Vue components."*)
<img src="https://vuejs.org/images/components.png " alt="Component tree" style="width:70%"/>

---

### What about our swapui app!

```bash
npm run serve
```

---

Replace the HelloWorld.vue content with
```html
<template>
    <div class="swapui">
        <h1>Swapui</h1>
    </div>
</template>

<script>
export default {
  name: 'Swapui'
}
</script>

<style scoped>
</style>
```

---

Rename HelloWorld.vue component to Swapui.vue

---

### @fa[cog fa-spin] Component props
Provide "A long time ago..." string from App to Swapui component and replace "Swapui" string with it

---

```html
<template>
    <div class="swapui">
        <h1>{{msg}}</h1>
    </div>
</template>

<script>
export default {
  name: 'Swapui',
  props:['msg'],
}
</script>

<style scoped>
</style>
```
--- 

```html
<template>
  <div id="app">
    <swapui msg="A long time ago..."/>
  </div>
</template>

<script>
import Swapui from './components/Swapui'

export default {
  name: 'app',
  components: {
    Swapui
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```
--- 
### @fa[cog fa-spin] Declarative rendering

Add a data attribute named date valued to current date and display it under the '&lt;h1&gt;...&lt;h1&gt;' line in a '&lt;h2&gt;&lt;/h2&gt;' element

Check what happens when you refresh the page

---

```javascript
data() {
    return {
        date: new Date()
    }
}
```

---

```html
<template>
    <div class="swapui">
        <h1>{{msg}}</h1>
        <h2>because we are {{date}}</h2>
    </div>
</template>

```
--- 
### @fa[cog fa-spin] External lib

Import momentjs lib and format current date to a pretty one

---

```javascript
import moment from 'moment'
```

```javascript
data () {
    return {
      date: moment().format('LLLL'),
    }
  }
```

---

![Alt](https://i.imgflip.com/lrvpo.jpg "darkstupidious")

---

```bash
This dependency was not found:
* moment in ./node_modules/cache-loader/dist/cjs.js??ref--12-0!./node_modules/babel-loader/lib!./node_modules/vue-loader/lib??vue-loader-options!./src/components/Swapui.vue?vue&type=script&lang=js&
To install it, you can run: npm install --save moment   
```
---

### @fa[cog fa-spin] Attribute binding

Add "This is the date" title to the date h2 element that we added bound to a new data element named 'dateTitle'

---

```html
<h2 v-bind:title="dateTitle">
```

```javascript
data () {
    return {
      date: moment().format('LLLL'),
      dateTitle: 'This is the date'
    }
  }
```

--- 

v-bind shortcut: ":'


```html
<h2 :title="dateTitle">

```

--- 

### @fa[cog fa-spin] Loops

Add an array of strings data element named "characters" which contains 'Boba Fett' and 'Leia Skywalker' items

Then display these elements in a div using v-for directive

```html
<!-- Sample -->
<div v-for="item in items"><span>{{character}}</span></div>

```

---

```html
<!-- ... -->
<div v-for="character in characters"><span>{{character}}</span></div>
<!-- ... -->
```

```javascript
data () {
    return {
      // ...
      characters: ['Boba Fett', 'Leia Skywalker']
      
    }
  }
```

--- 

ESLint compliation warning:

```bash
Module Warning (from ./node_modules/eslint-loader/index.js):
error: Elements in iteration expect to have 'v-bind:key' directives (vue/require-v-for-key) at src/components/Swapui.vue:5:9:
  3 |         <h1>{{msg}}</h1>
  4 |         <h2 v-bind:title="dateTitle">{{date}}</h2>
> 5 |         <div  v-for="character in characters"><span v-if="character !== 'Bobba Fett'">{{character}}</span></div>
    |         ^
  6 |     </div>
  7 | </template>
```

You have to provide vue with the collection elements identity property to tell Vue how to track nodes identity so existing elements can be reused and reordered

---

Not necessary for simple content according to VueJS doc, but ESLint stills throw a warning...

```html
<!-- ... -->
<div :key= "character" v-for="character in characters"><span>{{character}}</span></div>
<!-- ... -->
```

https://vuejs.org/v2/guide/list.html#key

---

### @fa[cog fa-spin] Conditionals

Add a condition with v-if directive in order not to display a character if named 'Boba Fett'

---

```html
<!-- ... -->
<div :key= "character" v-for="character in characters"><span v-if="character !== 'Bobba Fett'">{{character}}</span></div>

```

---

### Let's add some style 

Thanks to @vue/cli

```bash
$ vue add vuetify
? Use a pre-made template? (will replace App.vue and HelloWorld.vue) Yes
? Use custom theme? No
? Use a-la-carte components? No
? Use babel/polyfill? No

```

---