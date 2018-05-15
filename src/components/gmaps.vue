<template>
  <v-container grid-list-md text-xs-center>
    <h1 class="text-xs-center">Servicing Locations</h1>
    <v-layout
      wrap
      class="my-5"
      align-center
    >
      <v-flex xs12 sm6>
        <v-card dark color="secondary">
          <div id="gmaps">
            <br>
            <gmap-map
              :center="center"
              :zoom="12"
              style="width:100%;  height: 650px;"
            >
              <gmap-marker
                :key="index"
                v-for="(m, index) in markers"
                :position="m.position"
                @click="center=m.position"
              ></gmap-marker>
            </gmap-map>
          </div>
        </v-card>
      </v-flex>
      <v-flex xs6>
        <v-card dark color="secondary">
          <v-card-text class="px-0">6</v-card-text>
        </v-card>
      </v-flex>
     </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'GoogleMap',
  data () {
    return {
      // default to montreal to keep it simple
      // change this to whatever makes sense
      center: { lat: 34.1870, lng: -118.3818 },
      markers: [],
      places: [],
      currentPlace: null
    }
  },

  // mounted () {
  //   this.geolocate()
  // },

  methods: {
    setPlace (place) {
      this.currentPlace = place
    },
    addMarker () {
      if (this.currentPlace) {
        const marker = {
          lat: this.currentPlace.geometry.location.lat(),
          lng: this.currentPlace.geometry.location.lng()
        }
        this.markers.push({ position: marker })
        this.places.push(this.currentPlace)
        this.center = marker
        this.currentPlace = null
      }
    }
    // geolocate: function () {
    //   navigator.geolocation.getCurrentPosition(position => {
    //     this.center = {
    //       lat: position.coords.latitude,
    //       lng: position.coords.longitude
    //     }
    //   })
    // }
  }
}
</script>
