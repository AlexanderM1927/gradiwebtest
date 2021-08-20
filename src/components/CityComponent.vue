<template>
  <div class="city">
    <div class="row">
      <div class="col-3">
        <div class="my-weather">
          <img :src="'http://openweathermap.org/img/w/04d.png'">
        </div>
      </div>
      <div class="col-9">Texto</div>
    </div>
    <div class="row">
      <div class="col-4">X</div>
      <div class="col-4">X</div>
      <div class="col-4">X</div>
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
  background: white;
  color: black;
  border-radius: 20px;
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
</style>
