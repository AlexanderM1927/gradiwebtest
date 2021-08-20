<template>
  <div class="place">
    <b>Valle</b>
    <p>Europe</p>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PlaceToVisitMidComponent',
  data () {
    return {
    }
  }
})
</script>
<style lang="scss" scoped>
.place {
  margin-top: 10px;
  height: 130px;
  border-radius: 20px;
  background: url('../assets/placetovisitmid.jpg');
  // background-position-x: 5%;
  // background-position-y: 100%;
  background-size: cover;
  background-position: fixed;
  background-repeat: no-repeat;
  padding: 10px;
  color: white;
}
</style>
