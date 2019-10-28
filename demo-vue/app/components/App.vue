<template>
    <Page>
        <ActionBar title="NativeScript-Vue ❤️ Mapbox"/>
        <GridLayout columns="*" rows="*">
          <Mapbox
            :accessToken="accessToken"
            :mapStyle="mapStyle"
            @mapReady="onMapReady"
          ></Mapbox>
        </GridLayout>
    </Page>
</template>

<script >
  import * as Mapbox from 'nativescript-mapbox'

  export default {
    data() {
      return {
        accessToken: null, // TODO: ADD YOUR MAPBOX API TOKEN HERE
        mapStyle: "light",
      }
    },
    created() {
      // throw an error if Mapbox Access Token is not set
      if (!this.accessToken) {
        throw new Error('Your Mapbox accessToken is not set.  Add your token to the App.vue component data.')
      }
    },
    methods: {
      onMapReady(event) {
        console.log('Map Ready!')
        console.log('mapReady event: ', event) // log to console to inspect
      }
    }
  }
</script>

<style scoped>
    ActionBar {
        background-color: #53ba82;
        color: #ffffff;
    }

    .message {
        vertical-align: center;
        text-align: center;
        font-size: 20;
        color: #333333;
    }
</style>
