<template>
  <q-layout view="lHh Lpr lFf">
    <q-page-container>
      <!-- <router-view /> -->

    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    // EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
<style lang="scss" scoped>
body {
  font-family: Arial, Helvetica, sans-serif;
}
</style>