# nelo-mapbox-geocoder

nelo-mapbox-geocoder is a VueJS component for [mapbox-gl-geocoder](https://github.com/mapbox/mapbox-gl-geocoder) support.

## Installation

Use the package manager [npm](https://www.npmjs.com/) to install nelo-mapbox-geocoder.

```bash
npm i nelo-mapbox-geocoder
```

## Usage
```bash
<template>
  <div id="app">
    <nelo-mapbox-geocoder
            accessToken="YOUR_ACCESS_TOKEN"
            language="it"
            types="address,country"
            countries="it"
            :callback="getResults"
            placeholder="Search..."
    />
  </div>
</template>
<script>

  import Vue from 'vue';
  import NeloMapboxGeocoder from 'nelo-mapbox-geocoder.vue';

  export default Vue.extend({
    name: 'ServeDev',
    components: {
      NeloMapboxGeocoder
    },
    methods:{
      getResults(e){
        console.log(e);
      }
    }
  });
</script>
```
