<template>
  <div class="my-banner">
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
  background-position-y: 5%;
  background-size: 100%;
  background-position: fixed;
  background-repeat: no-repeat;
  color: #8d95f2;
  font-size: 20px;
  font-weight: bold;
  height: 300px;
  padding: 4.2% 4%;
}
.my-city-name {
  vertical-align: middle;
}
</style>
