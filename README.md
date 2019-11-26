# nuxt-polaris

> Nuxt module wrapper for [polaris-vue](https://github.com/EastsideCo/polaris-vue)

Allows you to use [Shopify Polaris](http://polaris.shopify.com/) components in [Vue 2](http://vuejs.org/).

This library currently contains components up-to-date with: _@shopify/polaris `v1.9.1`_



## Setup

1. Add `nuxt-polaris` dependency to your project

```bash
yarn add nuxt-polaris # or npm install nuxt-polaris
```

2. Add `nuxt-polaris` to the `modules` section of `nuxt.config.js`

```js
{
  modules: [
    // Simple usage
    'nuxt-polaris',

    // With options (CURRENTLY UNSUPPORTED)
    // ['{{ name }}', { /* module options */ }]
  ]
}
```



## Viewing the demo page
The demo page contains code examples of almost all the functionality in the library, so it can be pretty helpful.

To view the demo, open up `node_modules/nuxt-polaris/test/index.html` after installing the library.

Online version: http://demo.polaris-vue.eastsideco.io/

Or to create a standalone copy: clone the repo, run `npm run dev`, then open the file at `test/index.html`.



## Differences to @shopify/polaris

There are a few differences from the official react version you should be aware of:

#### 1. Naming for some attributes has been adjusted to be more Vue-like.
i.e. `Button` is `<polaris-button>`, `helpText` is `:help-text`, and `onDismiss` is `@dismiss`.

```
                     |  Polaris        |  Polaris-Vue     |
                     +-----------------+------------------+
Component            |  Banner         |  polaris-banner  |
Prop (HTML attr)     |  helpText       |  help-text       |
Prop (JS)            |  helpText       |  helpText        |
Event                |  onDismiss      |  @dismiss        |

```

#### 2. Attributes in the original library which accept ReactNodes have been implemented as both props and slots in this library, so you can include slot templates in them if needed.
```
<polaris-layout-section :description="Hello world!">
    <p>Body</p>
</polaris-layout-section>
```
```
<polaris-layout-section>
    <template slot="description">
        Hello <strong>world</strong>!
    </template>
    <p>Body</p>
</polaris-layout-section>
```

#### 3. Where render functions are passed to components (at the moment only ResourceList), this library instead uses scoped slots.
Check out the `<polaris-resource-list>` examples on the demo page for examples.

#### 4. No support for the Polaris EASDK integrations.
This library doesn't currently support complete integration with the EASDK.

You can still use this library in EASDK apps, but the page header will not be automatically hidden and synced with the EASDK header.

Support for the official behavior is planned.



## License

This library is provided 'as-is' under the terms of MIT license.
