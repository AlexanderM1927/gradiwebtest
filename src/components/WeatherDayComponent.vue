<template>
  <div class="my-day">
    Hola
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'WeatherDayComponent',
  data () {
    return {
    }
  }
})
</script>
<style lang="scss" scoped>
.my-day{
  margin: 5px;
  border: 1px solid #eaeaea;
  border-radius: 10px;
  padding: 5px;
}
</style>
