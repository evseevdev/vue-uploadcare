# Vue-uploadcare
Vue component for the Uploadcare widget.

# Requirements
- Vue.js `^2.3.0`

# Installation

## npm

```shell
$ npm install vue-uploadcare
```

# Usage
```html
<template>
  <div>
    <VueUploadcare :url.sync="photoUrl"></VueUploadcare>
  </div>
</template>

<script>
  import VueUploadcare from 'vue-uploadcare';

  export default {
    data() {
      return {
        photoUrl: ''
      }
    },
    components: { VueUploadcare }
  }
</script>