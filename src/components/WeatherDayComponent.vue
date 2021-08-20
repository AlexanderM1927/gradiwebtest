<template>
  <div class="my-day">
    <div class="row">
      <div class="col-8">
        <div class="my-padding-10">
          <div class="my-img-description">
            <div class="my-img">
              <img :src="'http://openweathermap.org/img/w/04d.png'">
            </div>
            <div class="my-text-description">
              <b>Friday</b>
              <p>Nublado</p>
            </div>
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
.my-img {
  float: left;
}
.my-img img {
  display: block;
}
.my-weather {
  font-size: 20px;
  padding: 10px 0px;
  word-break: break-word;
  text-align: center;
  background: #7c67ee;
  height: 100%;
  line-height: 40px;
  border-radius: 10px;
  color: white;
  font-weight: bold;
}
</style>
