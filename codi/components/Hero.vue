<template>
    <v-container>
      <v-row>
        <v-col>
          <v-carousel hide-delimiter-background show-arrows-on-hover >
            <v-carousel-item
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
              cover
            >
        
            <div class="d-flex fill-height justify-center align-center">
              <div class="text-h2" style="color:white">
                Centre exclusiu
              </div>
            </div>
        
          </v-carousel-item>
          
            <v-carousel-item
              src="https://cdn.vuetifyjs.com/images/cards/hotel.jpg"
              cover
            >
          
            <div class="d-flex fill-height justify-center align-center">
              <div class="text-h2" style="color:white">
                Tracte personalitzat
              </div>
            </div>
          </v-carousel-item>
          
            <v-carousel-item
              src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
              cover
            >
            <div class="d-flex fill-height justify-center align-center">
              <div class="text-h2" style="color:white">
                Els millors professionals
              </div>
            </div>
          </v-carousel-item>
          </v-carousel>
        </v-col>
      </v-row>
    </v-container>
  </template>