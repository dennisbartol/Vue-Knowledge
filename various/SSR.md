### SSR


SSR (<ins>Server-Side Rendering</ins>) refers to the process of rendering Vue components on the server and delivering fully rendered HTML to the browser, instead of relying solely on client-side rendering (CSR). This approach is particularly useful for improving performance, SEO, and user experience.

\
\
**How SSR Works in Vue 3**

**1. Server-Side Rendering:**<br>
A server runs the Vue app and generates an HTML string with the fully rendered components.

This HTML is sent to the client (browser), allowing users to see content immediately without waiting for JavaScript to load.



**2. Hydration:**<br>
Once the HTML is delivered, the browser downloads and executes the Vue.js JavaScript code.

Vue takes over the pre-rendered HTML and "hydrates" it, attaching event listeners and making the app interactive.


\
\
**Key Benefits of SSR**

**1. Better SEO:**</br>
Search engine crawlers can index the pre-rendered HTML, making it easier for your content to rank well in search engines.



**2. Improved Performance:**</br>
Users see content faster because the HTML is delivered directly, without waiting for JavaScript execution.



**3. Faster Time-to-Interactive:**</br>
While the server delivers content, hydration enables interactivity faster than loading an entirely client-rendered app.


\
\
**Vue 3 and SSR**

Vue 3 provides built-in support for SSR through its @vue/server-renderer package. This allows you to render Vue apps on the server.

\
Steps to Implement SSR in Vue 3

+ Set up a server:

Install the required dependencies:

```JS
npm install vue @vue/server-renderer express
```

Create a basic Express server:

```js
const express = require('express');
const { createSSRApp } = require('vue');
const { renderToString } = require('@vue/server-renderer');

const app = express();

app.get('*', async (req, res) => {
  const vueApp = createSSRApp({
    data: () => ({ message: 'Hello, SSR!' }),
    template: `<div>{{ message }}</div>`,
  });

  const html = await renderToString(vueApp);
  res.send(`<html><body>${html}</body></html>`);
});

app.listen(3000, () => {
  console.log('Server is running at http://localhost:3000');
});
```

\
**2. Hydration on the Client:**

Create a client-side Vue app to match the server-rendered content and hydrate it:

```JS
import { createApp } from 'vue';
import App from './App.vue';

const app = createApp(App);
app.mount('#app');
```

\
\
**Frameworks That Simplify SSR**

Instead of setting up SSR manually, you can use frameworks that streamline the process:

1. Nuxt.js: A framework built on Vue.js, designed specifically for SSR and static site generation (SSG).

2. Vite + SSR Plugins: Tools like vite-plugin-ssr simplify SSR with Vue 3.

\
**SSR vs. Other Rendering Strategies**

**1. Client-Side Rendering (CSR):** The entire app is rendered in the browser after JavaScript is downloaded.

**2. Static Site Generation (SSG):** HTML is generated at build time and served as static files, offering fast performance without requiring a server.

**3. ISR (Incremental Static Regeneration):** Combines SSG and SSR, allowing certain pages to be rendered dynamically while others remain static.

\
Vue 3's SSR capabilities make it ideal for building high-performance, SEO-friendly web applications that deliver a great user experience.

