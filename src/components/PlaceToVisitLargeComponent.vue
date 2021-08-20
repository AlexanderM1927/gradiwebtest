<template>
  <div class="place">
    <b>Arab Street</b>
    <p>Singapoor</p>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PlaceToVisitLargeComponent',
  data () {
    return {
    }
  }
})
</script>
<style lang="scss" scoped>
.place {
  height: 265px;
  border-radius: 20px;
  background: url('../assets/placetovisit.jpeg');
  // background-position-x: 5%;
  // background-position-y: 100%;
  background-size: cover;
  background-position: fixed;
  background-repeat: no-repeat;
  padding: 10px;
  color: white;
}
</style>
