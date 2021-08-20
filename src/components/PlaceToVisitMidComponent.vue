<template>
  <div class="place">
    <div class="my-text">
      <b>Valle</b>
      <p>Europe</p>
    </div>
    <div @click="$emit('showModalAddPlaces')" class="my-btn-add">
      <q-icon name="add"/>
    </div>
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
  margin-top: 30px;
  height: 138px;
  border-radius: 20px;
  background: url('../assets/placetovisitmid.jpg');
  // background-position-x: 5%;
  // background-position-y: 100%;
  background-size: cover;
  background-position: fixed;
  background-repeat: no-repeat;
  padding: 10px;
  color: white;
  margin-bottom: 10px;
}
.my-text {
  float: left;
}
.my-btn-add {
  float: right;
  height: 138px;
  margin-right: -10px;
  border-radius: 20px;
  background: #7c67ee;
  margin-top: -10px;
  width: 20%;
  text-align: center;
  justify-content: center;
  vertical-align: middle;
  line-height: 130px;
  cursor: pointer;
  position: relative;
}
</style>
