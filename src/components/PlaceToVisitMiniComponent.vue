<template>
  <div class="place">
    <b>Neighborhood</b>
    <p>Venecia</p>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PlaceToVisitMiniComponent',
  data () {
    return {
    }
  }
})
</script>
<style lang="scss" scoped>
.place {
  height: 100px;
  border-radius: 20px;
  background: url('../assets/placetovisitmini.jpeg');
  // background-position-x: 5%;
  // background-position-y: 100%;
  background-size: cover;
  background-position: fixed;
  background-repeat: no-repeat;
  padding: 10px;
  color: white;
}
</style>
