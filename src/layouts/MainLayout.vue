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
        <widget-component v-if="weatherMainCity" :weather="weatherMainCity" class="animate__animated animate__slideInLeft"></widget-component>
        <banner-component class="animate__animated animate__slideInLeft"></banner-component>
        <div class="row my-containers animate__animated animate__slideInLeft">
          <div class="col-md-9 col-xs-12">
            <div class="row">
              <div class="col-md-3 col-xs-12">
                <div class="text-h6">
                  <b>3 Days</b> Forecast
                </div>
                <div class="my-mt-10">
                  <weather-day-component v-if="weatherFirstDay" :day="weatherFirstDay" :isFirstDay="true"></weather-day-component>
                  <weather-day-component v-if="weatherSecondDay" :day="weatherSecondDay"></weather-day-component>
                  <weather-day-component v-if="weatherThirdDay" :day="weatherThirdDay"></weather-day-component>
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
            <div :class="$q.screen.xs || $q.screen.sm ? '' : 'my-container-floating'">
              <city-component v-if="weatherLyonCity" :city="weatherLyonCity"></city-component>
              <city-component v-if="weatherParisCity" :city="weatherParisCity"></city-component>
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
import { date } from 'quasar'
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
      modalAddPlace: false,
      weatherMainCity: null,
      weatherLyonCity: null,
      weatherParisCity: null,
      weatherFirstDay: null,
      weatherSecondDay: null,
      weatherThirdDay: null
    }
  },
  mounted () {
    this.getWeatherMainCity()
    this.getWeatherLyonCity()
    this.getWeatherParisCity()
    this.getForecast()
  },
  methods: {
    getWeatherMainCity () {
      const xhttp = new XMLHttpRequest()
      xhttp.onload = (response) => {
        this.weatherMainCity = JSON.parse(response.target.response)
      }
      xhttp.open('GET', 'https://api.openweathermap.org/data/2.5/weather?q=bogota&appid=2feec8ba20ee284ee9c81255cddb20b4&units=metric')
      xhttp.send()
    },
    getWeatherLyonCity () {
      const xhttp = new XMLHttpRequest()
      xhttp.onload = (response) => {
        this.weatherLyonCity = JSON.parse(response.target.response)
        console.log('this.weatherLyonCity')
        console.log(this.weatherLyonCity)
      }
      xhttp.open('GET', 'https://api.openweathermap.org/data/2.5/weather?q=lyon&appid=2feec8ba20ee284ee9c81255cddb20b4&units=metric')
      xhttp.send()
    },
    getWeatherParisCity () {
      const xhttp = new XMLHttpRequest()
      xhttp.onload = (response) => {
        this.weatherParisCity = JSON.parse(response.target.response)
      }
      xhttp.open('GET', 'https://api.openweathermap.org/data/2.5/weather?q=paris&appid=2feec8ba20ee284ee9c81255cddb20b4&units=metric')
      xhttp.send()
    },
    getForecast () {
      const xhttp = new XMLHttpRequest()
      xhttp.onload = async (response) => {
        const resIntoJsonFormat = JSON.parse(response.target.response)
        const weatherDays = this.getNextDays(resIntoJsonFormat.list)
        this.weatherFirstDay = weatherDays[0]
        this.weatherSecondDay = weatherDays[1]
        this.weatherThirdDay = weatherDays[2]
      }
      xhttp.open('GET', 'https://api.openweathermap.org/data/2.5/forecast?q=bogota&appid=2feec8ba20ee284ee9c81255cddb20b4&units=metric')
      xhttp.send()
    },
    getNextDays (list) {
      if (list) {
        const res = []
        for (let index = 0; index < list.length; index++) {
          if (this.isIntoNextDays(list[index]) && !this.isDayIntoList(res, list[index])) res.push(list[index])
        }
        return res
      }
    },
    isIntoNextDays (value) {
      let res = false
      const { addToDate } = date
      const dateIntoThreeDays = addToDate(new Date(), { days: 3 })
      if (new Date(value.dt_txt) <= dateIntoThreeDays && new Date(value.dt_txt) > addToDate(new Date(), { days: 1 })) res = true
      return res
    },
    isDayIntoList (list, day) {
      let res = false
      for (let index = 0; index < list.length; index++) {
        if (date.isSameDate(list[index].dt_txt, day.dt_txt, 'day')) {
          res = true
          break
        }
      }
      return res
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
