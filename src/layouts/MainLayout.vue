<template lang="pug">
q-layout
  q-page
    router-view
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'MainLayout',
  setup () {
    return {
    }
  }
})
</script>
