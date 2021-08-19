<template>
  <q-layout class="my-layout" view="lHh Lpr lFf">
    <q-page-container>
      <!-- <router-view /> -->
      <div class="row">
        <div class="col-md-11 col-xs-9"></div>
        <div class="col-md-1 col-xs-3">
          <center>
            <img src="../assets/logo.png">
          </center>
        </div>
      </div>
      <div class="my-main-box">
        <widget-component></widget-component>
        <banner-component></banner-component>
        <div class="row my-containers">
          <div class="col-md-9 col-xs-12">
            Hola
          </div>
          <div class="col-md-3 col-xs-12">
            <div class="my-container-floating">
              Hola
            </div>
          </div>
        </div>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue'
import BannerComponent from '../components/BannerComponent'
import WidgetComponent from '../components/WidgetComponent'

export default defineComponent({
  name: 'MainLayout',

  components: {
    // EssentialLink
    BannerComponent,
    WidgetComponent
  },

  // setup () {
  //   const leftDrawerOpen = ref(false)

  //   return {
  //     essentialLinks: linksList,
  //     leftDrawerOpen,
  //     toggleLeftDrawer () {
  //       leftDrawerOpen.value = !leftDrawerOpen.value
  //     }
  //   }
  // }
  data () {
    return {
      text: 'Hello world'
    }
  }
})
</script>
<style lang="scss" scoped>

.my-layout {
  font-family: Arial, Helvetica, sans-serif;
  background: linear-gradient(to right, #dce3eb 30%, #d3d9e0 50%);
  height: 100%;
}
.my-main-box {
  background: white;
  padding: 2%;
  margin: 1% 4%;
  border-radius: 20px;
}
.my-containers {
  margin-top: 20px;
}
.my-container-floating {
  position: absolute;
  margin-top: -40px;
}
</style>
