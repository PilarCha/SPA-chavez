<template>
  <v-container grid-list-md text-xs-center id="gmaps">
    <h1 class="text-xs-center">Servicing Locations</h1>
    <v-layout
      wrap
      class="my-5"
      align-center
    >
      <v-flex xs12 sm6>
        <v-card dark color="secondary">
          <div>
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

      <!-- right side box -->

      <v-flex xs6>
        <v-card dark color="secondary">
          <div
            id="e3"
            style="width: auto; margin: auto; height:650px;"
            class="grey lighten-3"
          >
            <v-card>
              <v-container
                fluid
                style="min-height: 0, height: 650px;"
                grid-list-lg
              >
                <v-layout row wrap>
                  <v-flex xs12>
                    <v-card color="blue-grey darken-2" class="white--text">
                      <v-card-title primary-title>
                        <div class="headline">Unlimited music now</div>
                        <div>Listen to your favorite artists and albums whenever and wherever, online and offline.</div>
                      </v-card-title>
                      <v-card-actions>
                        <v-btn flat dark>Listen now</v-btn>
                      </v-card-actions>
                    </v-card>
                  </v-flex>
                  <v-flex xs12>
                    <v-card color="cyan darken-2" class="white--text">
                      <v-container fluid grid-list-lg>
                        <v-layout row>
                          <v-flex xs7>
                            <div>
                              <div class="headline">Supermodel</div>
                              <div>Foster the People</div>
                            </div>
                          </v-flex>
                          <v-flex xs5>
                            <v-card-media
                              src="/static/doc-images/cards/foster.jpg"
                              height="125px"
                              contain
                            ></v-card-media>
                          </v-flex>
                        </v-layout>
                      </v-container>
                    </v-card>
                  </v-flex>
                  <v-flex xs12>
                    <v-card color="purple" class="white--text">
                      <v-container fluid grid-list-lg>
                        <v-layout row>
                          <v-flex xs7>
                            <div>
                              <div class="headline">Halycon Days</div>
                              <div>Ellie Goulding</div>
                            </div>
                          </v-flex>
                          <v-flex xs5>
                            <v-card-media
                              src="/static/doc-images/cards/halcyon.png"
                              height="125px"
                              contain
                            ></v-card-media>
                          </v-flex>
                        </v-layout>
                      </v-container>
                    </v-card>
                  </v-flex>
                </v-layout>
              </v-container>
            </v-card>
          </div>
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
      center: { lat: 34.1870, lng: -118.3818 },
      markers: [],
      places: [],
      currentPlace: null
    }
  },

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
  }
}
</script>
