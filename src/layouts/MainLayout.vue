<template>
  <q-layout class="my-layout" view="lHh Lpr lFf">
    <q-page-container>
      <!-- <router-view /> -->
      <div class="row">
        <div class="col-md-11 col-xs-9"></div>
        <div class="col-md-1 col-xs-3 my-center animate__animated animate__fadeIn">
          <img src="../assets/logo.png">
        </div>
      </div>
      <div class="my-main-box">
        <widget-component class="animate__animated animate__slideInLeft"></widget-component>
        <banner-component class="animate__animated animate__slideInLeft"></banner-component>
        <div class="row my-containers animate__animated animate__slideInLeft">
          <div class="col-md-9 col-xs-12">
            <div class="row">
              <div class="col-md-3 col-xs-12">
                <div class="text-h6">
                  <b>3 Days</b> Forecast
                </div>
                <div class="my-mt-10">
                  <weather-day-component :day="firstDay"></weather-day-component>
                  <weather-day-component :day="secondDay"></weather-day-component>
                  <weather-day-component :day="thirdDay"></weather-day-component>
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
                  <div class="row">
                    <div class="col-6">
                      <b>Top reviews</b>
                    </div>
                    <div class="col-6">
                      <div class="my-avatars-list">
                        <q-avatar class="my-avatar" rounded>
                          <img src="https://cdn.quasar.dev/img/avatar.png">
                        </q-avatar>
                        <q-avatar class="my-avatar" rounded>
                          <img src="https://cdn.quasar.dev/img/avatar.png">
                        </q-avatar>
                        <q-avatar class="my-avatar" rounded>
                          <img src="https://cdn.quasar.dev/img/avatar.png">
                        </q-avatar>
                        <q-avatar class="my-avatar" rounded>
                          +5
                        </q-avatar>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="my-mt-10">
                  <place-to-visit-mini-component></place-to-visit-mini-component>
                  <place-to-visit-mid-component @showModalAddPlaces="modalAddPlace = true"></place-to-visit-mid-component>
                </div>
              </div>
              <div class="col-md-1 col-xs-12"></div>
            </div>
          </div>
          <div class="col-md-3 col-xs-12">
            <div :class="$q.screen.xs ? '' : 'my-container-floating'">
              <city-component></city-component>
              <city-component></city-component>
              <add-city-component></add-city-component>
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
import AddCityComponent from '../components/AddCityComponent'
import 'animate.css'
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
    CityComponent,
    AddCityComponent
  },
  data () {
    return {
      text: 'Hello world',
      firstDay: {
        isNextDay: true
      },
      secondDay: {
        isNextDay: false
      },
      thirdDay: {
        isNextDay: false
      },
      modalAddPlace: false
    }
  },
  mounted () {
    this.getWeatherMainCity()
  },
  methods: {
    getWeatherMainCity () {
      const xhttp = new XMLHttpRequest()
      xhttp.onload = (response) => {
        console.log(JSON.parse(response.target.response))
      }
      xhttp.open('GET', 'https://api.openweathermap.org/data/2.5/weather?q=bogota&appid=2feec8ba20ee284ee9c81255cddb20b4&units=metric')
      xhttp.send()
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
  margin-top: -120px;
  width: 90%;
}
.my-mt-10 {
  margin-top: 10px;
}
.my-title-reviews {
  font-size: 17px;
  line-height: 30px;
  color: #c6c6c5;
}
.my-avatar {
  height: 30px;
  width: 30px;
  background: #b3a8e7;
  color: white;
  margin-left: 2px;
}
.my-avatars-list {
  margin-left: 28px;
}
</style>
