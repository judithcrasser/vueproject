<template>
  <div class="hero-section">
    <h1>
      Frontends we like!
    </h1>
  </div>

  <Accordion />
  <AppTab />

</template>


<script>
import Accordion from '../components/Accordion.vue'
import AppTab from '../components/AppTab.vue'

export default {
  components: {
    Accordion,
    AppTab
  },
}

</script>