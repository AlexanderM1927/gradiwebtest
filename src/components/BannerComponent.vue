<template>
  <div class="my-banner" :style="$q.screen.xs ? 'background-position-x: 70%;' : 'background-position-x: 100%;'">
    <div class="my-city-name"><q-icon name="place"/>{{text}}</div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'BannerComponent',
  data () {
    return {
      text: 'Bogota'
    }
  }
})
</script>
<style lang="scss" scoped>
.my-banner {
  border-radius: 20px;
  background: url('../assets/bg-banner.png') bottom #a1c8d0;
  background-position-x: 100%;
  background-position-y: 10%;
  // background-size: cover;
  background-position: fixed;
  background-repeat: no-repeat;
  color: #8d95f2;
  font-size: 20px;
  font-weight: bold;
  height: 50%;
  padding: 75px 65px;
}
.my-city-name {
  vertical-align: middle;
}
</style>
