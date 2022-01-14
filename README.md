# FocusTrap

> A Vue component that traps focus

This component is a light wrapper around [focus-trap](https://github.com/davidtheclark/focus-trap), tailored to your Vue-specific needs.

Forked from the no longer maintained [wovue-focus-trap](https://wovue.github.io/focus-trap)

## Live examples & Docs

[Documentation can be viewed at http://beta.viafoura.com/focus-trap/](http://beta.viafoura.com/focus-trap/)

## Features

* The focus trap automatically activates on ready hook (by default, though this can be changed).
* The focus trap automatically deactivates on destroyed hook.
* The focus trap can be activated and deactivated, paused and unpaused via props.

## Getting Started

Please read [the focus-trap documentation](https://github.com/davidtheclark/focus-trap#focus-trap) to understand what a focus trap is, what happens when a focus trap is activated, and what happens when one is deactivated.


### NPM + AWS CodeArtifact

Install Node v12.22.x, NPM v6.14.x. At this point in time, Node 12 is as high as we can go due to our dependencies.

Install this package using npm as usual, but be logged into CodeArtifact via the AWS CLI.

```sh
# NEW
$ aws codeartifact login --tool npm --domain viafoura --repository viafoura-repository --namespace vf
$ npm install --save @vf/vue-focus-trap

# OLD
$ npm install --save @viafoura/vue-focus-trap
```

**NOTES:**

* The login command will ask you for an MFA code.
* This config will be valid for twelve (12) hours.
* [VF AWS Access Documentation](https://sites.google.com/a/viafoura.com/wiki/engineering/aws-access?authuser=0&pli=1)

Install the plugin

```js
import Vue from 'vue';
import { FocusTrap } from '@vf/vue-focus-trap';

// Use it as a global component...
Vue.component('focus-trap', FocusTrap);

// Or as a local component:
export const MyComponent = {
  // ...
  components: {
    FocusTrap
  }
  // ...
}
```

### Browser

TODO

## Basic Usage

```html
<button @click="mountTrap">mount trap</button>
<wv-focus-trap v-if="isTrapVisible" :active="isTrapActive">
  <p>Here is a focus trap <a href='#!'>with</a> <a href='#!'>some</a> <a href='#!'>focusable</a> parts.</p>
  <button @click="toggleTrap">toggle trap</button>
</wv-focus-trap>
```

```js
import { FocusTrap } from '@vf/vue-focus-trap';

export default {
  data () {
    return {
      isTrapVisible: false,
      isTrapActive: true
    };
  },
  methods: {
    mountTrap () {
      this.isTrapVisible = true;
    },
    toggleTrap () {
      this.isTrapActive = !this.isTrapActive;
    },
  },
  components: {
    FocusTrap
  },
};
```

## Development

``` bash
# install dependencies
aws codeartifact login --tool npm --domain viafoura --repository viafoura-repository --namespace vf
npm install

# serve with hot reload src-docs at localhost:8080
npm run dev

# build for production with minification src-docs and src
npm run build

# copy docs folder to gh-pages branch and push
npm run deploy-docs
```
