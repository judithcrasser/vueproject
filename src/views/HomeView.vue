<template>
  <HeroSection />
  <AccordionTest />
  <Accordion />
  <AppTab />
</template>


<script>
import Accordion from '../components/Accordion/Accordion.vue'
import AppTab from '../components/AppTab.vue'
import HeroSection from '../components/HeroSection.vue';
import AccordionTest from '../components/AccordionTest.vue';


export default {
  components: {
    Accordion,
    AppTab,
    HeroSection,
    AccordionTest

  },
}

</script>