<template>
  <div class="city">
    <div class="row">
      <div class="col-3">Imagen</div>
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
</style>
