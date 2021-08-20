<template>
  <div class="city">
    <div class="row">
      <div class="col-3">
        <div class="my-weather">
          <img :src="'http://openweathermap.org/img/w/' + city.weather[0].icon +'.png'">
        </div>
      </div>
      <div class="col-9">
        <div class="my-des">
          <div class="my-weather-number">
            {{Math.round(city.main.temp)}}°ᶜ
          </div>
          <div class="my-city">
            <b style="font-size: 16px;">{{city.name}}</b><br>
            {{city.sys.country}}
          </div>
        </div>
      </div>
    </div>
    <div class="row text-center my-color-gray my-city-dates">
      <div class="col-4 my-border-right">Humidity: {{city.main.humidity}}%</div>
      <div class="col-4 my-border-right">{{city.name === 'Paris' ? 'West' : 'Northwest'}}</div>
      <div class="col-4">{{city.wind.speed * 100}}km/h</div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CityComponent',
  props: ['city'],
  data () {
    return {
    }
  }
})
</script>
<style lang="scss" scoped>
.city {
  margin-bottom: 15px;
  background: white;
  color: black;
  border-radius: 20px;
  box-shadow: 0 0px 0px 0 rgba(0,0,0,.14), 0 0px 10px 0 rgba(0,0,0,.12), 0 2px 4px -1px rgba(0,0,0,.3);
}
.my-weather {
  font-size: 20px;
  padding: 10px 0px;
  word-break: break-word;
  text-align: center;
  background: #daebf0;
  height: 100%;
  // line-height: 40px;
  border-radius: 10px;
  color: white;
  font-weight: bold;
}
.my-color-gray {
  color: #c5c5c4;
}
.my-city {
  max-height: 50px;
}
.my-city-dates {
  font-weight: bold;
  padding: 10px;
}
.my-des {
  padding: 15px;
}
.my-weather-number {
  text-align: center;
  float: left;
  width: auto;
  height: 100%;
  padding: 5px;
  border-right: 1px solid #eaeaea;
  margin-right: 5px;
  font-size: 30px;
}
.my-border-right {
  border-right: 1px solid #eaeaea;
}
</style>
