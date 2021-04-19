<template>
  <div>
    <header>
      <app-header />
      <app-nav />
    </header>
    <nuxt />
  </div>
</template>

<script>
import AppNav from '~/components/AppNav.vue'
import AppHeader from '~/components/AppHeader.vue'

export default {
  components: {
    AppNav,
    AppHeader,
  },
}
</script>

<style>
html {
  font-family: 'Open Sans', sans-serif;
  font-size: 18px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

body {
  background: url('/body_bg_basketball.jpeg') no-repeat center top;
  background-color: #17375f;
  background-size: 100%;
}

h1,
h2,
h3 {
  margin: 0 0 20px;
  color: #34495e;
  font-family: 'Roboto Condensed', Arial Narrow, Arial, sans-serif;
  font-weight: 600;
  line-height: 1.2em;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.individual h3 {
  margin: 2em 0 25px;
}

header {
  position: relative;
  width: 100%;
  max-width: 1060px;
  margin: 0px auto;
  padding: 0px 20px;
}

h1 {
  line-height: 1.2em;
  margin-bottom: 30px;
  text-align: left;
}

img {
  width: 100%;
}

video {
  width: 100%;
  margin: 25px 0;
}

small {
  color: #9d5615;
}

pre,
code {
  white-space: pre-wrap; /* css-3 */
  white-space: -moz-pre-wrap; /* Mozilla, since 1999 */
  white-space: -pre-wrap; /* Opera 4-6 */
  white-space: -o-pre-wrap; /* Opera 7 */
  word-wrap: break-word; /* Internet Explorer 5.5+ */
  background: #eee;
  border-radius: 4px;
}

pre {
  padding: 8px 10px;
}

code {
  padding: 2px 0;
  line-height: 1.5;
}

p {
  margin: 15px 0 20px;
}
</style>
