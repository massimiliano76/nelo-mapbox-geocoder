<script>

    import mapboxgl from "mapbox-gl";
    import MapboxGeocoder from '@mapbox/mapbox-gl-geocoder';
    import '@mapbox/mapbox-gl-geocoder/dist/mapbox-gl-geocoder.css'

    export default {
        props: {
            accessToken: String,
            language: String,
            types: String,
            countries: String,
            placeholder: String,
            callback: Function,
        },
        name: 'NeloMapboxGeocoder', // vue component name
        data() {
            return {};
        },
        mounted() {

            mapboxgl.accessToken = this.accessToken;
            var geocoder = new MapboxGeocoder({
                accessToken: mapboxgl.accessToken,
                types: this.types,
                countries: this.countries,
                language: this.language,
                placeholder: this.placeholder
            });

            geocoder.addTo('#geocoder');

            let that = this;

            geocoder.on('result', function (ev) {
                that.callback(ev);
            });

        },
        computed: {},
        methods: {},

    };
</script>

<template>
    <div id="nelo-mapbox-geocoder">
        <div id="geocoder"></div>
    </div>
</template>

<style scoped>
    #nelo-mapbox-geocoder{
        margin: 0 auto;
    }
    #nelo-mapbox-geocoder #geocoder{
        width: 100%;
    }
</style>
