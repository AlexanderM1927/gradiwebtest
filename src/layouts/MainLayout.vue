<template>
  <q-layout class="my-layout" view="lHh Lpr lFf">
    <q-page-container>
      <!-- <router-view /> -->
      <div class="row">
        <div class="col-md-11 col-xs-9"></div>
        <div class="col-md-1 col-xs-3">
          <center>
            <img src="../assets/logo.png">
          </center>
        </div>
      </div>
      <div class="my-main-box">
        <widget-component></widget-component>
        <banner-component></banner-component>
        <div class="row my-containers">
          <div class="col-md-9 col-xs-12">
            <div class="row">
              <div class="col-md-3 col-xs-12">
                <div class="text-h6">
                  <b>3 Days</b> Forecast
                </div>
                <div class="my-mt-10">
                  <weather-day-component></weather-day-component>
                  <weather-day-component></weather-day-component>
                  <weather-day-component></weather-day-component>
                </div>
              </div>
              <div class="col-md-1 col-xs-12"></div>
              <div class="col-md-3 col-xs-12">
                <div class="text-h6">
                  <b>Place to</b> Visit.
                </div>
                <div class="my-mt-10">
                  <place-to-visit-large-component></place-to-visit-large-component>
                </div>
              </div>
              <div class="col-md-1 col-xs-12"></div>
              <div class="col-md-3 col-xs-12">
                <div class="my-title-reviews">
                  <b>Top reviews</b>
                </div>
                <div class="my-mt-10">
                  <place-to-visit-mini-component></place-to-visit-mini-component>
                  <place-to-visit-mid-component></place-to-visit-mid-component>
                </div>
              </div>
              <div class="col-md-1 col-xs-12"></div>
            </div>
          </div>
          <div class="col-md-3 col-xs-12">
            <div :class="$q.screen.xs ? '' : 'my-container-floating'">
              <city-component></city-component>
              <city-component></city-component>
            </div>
          </div>
        </div>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue'
import BannerComponent from '../components/BannerComponent'
import WidgetComponent from '../components/WidgetComponent'
import WeatherDayComponent from '../components/WeatherDayComponent'
import PlaceToVisitLargeComponent from '../components/PlaceToVisitLargeComponent'
import PlaceToVisitMiniComponent from '../components/PlaceToVisitMiniComponent'
import PlaceToVisitMidComponent from '../components/PlaceToVisitMidComponent'
import CityComponent from '../components/CityComponent'

export default defineComponent({
  name: 'MainLayout',

  components: {
    // EssentialLink
    BannerComponent,
    WidgetComponent,
    WeatherDayComponent,
    PlaceToVisitLargeComponent,
    PlaceToVisitMiniComponent,
    PlaceToVisitMidComponent,
    CityComponent
  },

  // setup () {
  //   const leftDrawerOpen = ref(false)

  //   return {
  //     essentialLinks: linksList,
  //     leftDrawerOpen,
  //     toggleLeftDrawer () {
  //       leftDrawerOpen.value = !leftDrawerOpen.value
  //     }
  //   }
  // }
  data () {
    return {
      text: 'Hello world'
    }
  }
})
</script>
<style lang="scss" scoped>

.my-layout {
  font-family: Arial, Helvetica, sans-serif;
  background: linear-gradient(to right, #dce3eb 30%, #d3d9e0 50%);
  height: 100%;
}
.my-main-box {
  background: white;
  padding: 2%;
  margin: 1% 4%;
  border-radius: 20px;
}
.my-containers {
  margin-top: 25px;
}
.my-container-floating {
  // position: absolute;
  margin-top: -60px;
}
.my-mt-10 {
  margin-top: 10px;
}
.my-title-reviews {
  font-size: 17px;
  line-height: 30px;
  color: #c6c6c5;
}
</style>
