<template>
  <div class="city">
    <div class="row">
      <div class="col-12 my-center">
        <q-btn no-caps outline rounded color="primary" label="Add location" />
      </div>
    </div>
    <div class="row">
      <div class="col-12">
        <img class="my-img my-center" src="../assets/add-city.jpg">
      </div>
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
  margin-bottom: 15px;
  background: white;
  color: black;
  border: 1px solid #eaeaea;
  border-radius: 20px;
  padding: 15px;
  // box-shadow: 0 0px 0px 0 rgba(0,0,0,.14), 0 0px 10px 0 rgba(0,0,0,.12), 0 2px 4px -1px rgba(0,0,0,.3);
}
.my-img {
  height: auto;
  width: auto;
  max-width: 100px;
  max-height: 100px;
  display: block;
}
.my-center {
  text-align: center;
  justify-content: center;
  align-content: center;
  align-items: center;
  margin-left: auto;
  margin-right: auto;
}
</style>
