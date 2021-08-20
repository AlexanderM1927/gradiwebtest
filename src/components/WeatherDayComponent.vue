<template>
  <div class="my-day">
    <div class="row">
      <div class="col-8">
        <div class="my-padding-10">
          <div class="my-img-description">
            <div class="my-img">
              <img :src="'http://openweathermap.org/img/w/' + day.weather[0].icon + '.png'">
            </div>
            <div class="my-text-description">
              <b>{{getTextFromDay(day.dt_txt)}}</b>
              <p>{{day.weather[0].main}}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="col-4">
        <div :class="'my-weather vertical-middle ' + (isFirstDay ? 'my-next-day' : 'my-another-day')">
          {{Math.round(day.main.temp_max)}}°/{{Math.round(day.main.temp_min)}}°
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import { date } from 'quasar'

export default defineComponent({
  name: 'WeatherDayComponent',
  props: ['day', 'isFirstDay'],
  data () {
    return {
    }
  },
  methods: {
    getTextFromDay (day) {
      const formattedString = date.formatDate(new Date(day), 'dddd')
      return formattedString
    }
  }
})
</script>
<style lang="scss" scoped>
.my-day{
  margin-top: 10px;
  margin-bottom: 10px;
  border: 1px solid #eaeaea;
  border-radius: 10px;
  // padding: 10px;
}
.my-img {
  float: left;
}
.my-img img {
  display: block;
}
.my-weather {
  font-size: 20px;
  padding: 10px 0px;
  word-break: break-word;
  text-align: center;
  height: 100%;
  line-height: 60px;
  border-radius: 10px;
  color: white;
  font-weight: bold;
}
.my-next-day {
  background: #7c67ee;
}
.my-another-day {
  background: #daebf0;
  color: black;
}
.my-img-description {
  vertical-align: middle;
  align-items: center;
  line-height: 22px;
}
</style>
