<template>
  <div class="city">
    <div class="row">
      <div class="col-3">
        <div class="my-weather">
          <img :src="'http://openweathermap.org/img/w/04d.png'">
        </div>
      </div>
      <div class="col-9">
        <div class="my-des">
          <div class="my-weather-number">
            29°ᶜ
          </div>
          <div class="my-city">
            <b style="font-size: 16px;">Lyon</b><br>
            Francia
          </div>
        </div>
      </div>
    </div>
    <div class="row text-center my-color-gray my-city-dates">
      <div class="col-4 my-border-right">Humidity: 48%</div>
      <div class="col-4 my-border-right">Northwast</div>
      <div class="col-4">83km/h</div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CityComponent',
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
