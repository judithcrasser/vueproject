<template>
  <HeroSection />
  <AccordionTest />
  <Accordion />
  <AppTab />
  <Gallery />
</template>


<script>
import Accordion from '../components/Accordion/Accordion.vue'
import AppTab from '../components/AppTab.vue'
import HeroSection from '../components/HeroSection.vue';
import Gallery from '../components/Gallery/Gallery.vue'
import AccordionTest from '../components/AccordionTest.vue';


export default {
  components: {
    Accordion,
    AppTab,
    HeroSection,
    Gallery,
    HeroSection,
    AccordionTest
  },
}

</script>