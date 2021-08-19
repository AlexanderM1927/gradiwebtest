<template>
  <div class="my-day">
    <div class="row">
      <div class="col-8">
        <div class="my-padding-10">
          <div class="my-img-description">
            <img :src="'http://openweathermap.org/img/w/04d.png'">
          </div>
        </div>
      </div>
      <div class="col-4">
        <div class="my-weather">
          32°/23°
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'WeatherDayComponent',
  data () {
    return {
    }
  }
})
</script>
<style lang="scss" scoped>
.my-day{
  margin: 5px;
  border: 1px solid #eaeaea;
  border-radius: 10px;
  // padding: 10px;
}
.my-img-description {}
.my-weather {
  font-size: 25px;
  padding: 10px;
  background: #7c67ee;
  height: 100%;
  border-radius: 10px;
  color: white;
  font-weight: bold;
}
</style>
