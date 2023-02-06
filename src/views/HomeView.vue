<template>
  <div class="hero-section">
    <h1>
      Frontends we like!
    </h1>
  </div>

  <Accordion />
  <TabsOutput />

</template>


<script>
import Accordion from '../components/Accordion.vue'
import TabsOutput from '../components/TabsOutput.vue'

export default {
  components: {
    Accordion,
    TabsOutput
  },
}

</script>