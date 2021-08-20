<template>
  <div class="my-widget">
    <div class="box arriba">
      <img :src="'http://openweathermap.org/img/w/' + weather.weather[0].icon + '.png'">
    </div>
    <div class="box abajo">{{Math.round(weather.main.temp)}}</div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'WidgetComponent',
  props: ['weather'],
  data () {
    return {
      text: 'Bogota'
    }
  },
  mounted () {
  }
})
</script>
<style lang="scss" scoped>
.my-widget {
  position: absolute;
  left: 4%;
  margin-top: 30px;
  width: 72px;
  background: #7d68e6;
  border-radius: 10px 10px 0px 0px;
  z-index: 2;
}
.box {
  border-radius: 0px 10px 10px 0px;
  padding: 10px;
  color: white;
  text-align: center;
}
.arriba {
  background: #31338a;
  vertical-align: middle;
  line-height: 0px;
}
.abajo {
  background: #7d68e6;
  font-size: 25px;
  font-weight: bold;
}
</style>
