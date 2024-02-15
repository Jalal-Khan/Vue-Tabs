<script setup>
import TabsWrapper from './components/TabsWrapper.vue';
import Tab from './components/Tab.vue';
import carousel from './components/carousel.vue';
import autoCarousel from './components/autoCarousel.vue';
</script>

<template>
  <div>

    <TabsWrapper>
      <Tab title="Tab 1">Hello from Tab 1</Tab>
      <Tab title="Tab 2">Hello from Tab 2</Tab>
      <Tab title="Tab 3">Hello from Tab 3</Tab>
      <Tab title="Tab 4">Hello from Tab 4</Tab>
    </TabsWrapper>
    <h2>The above is reusable tabs component</h2>
    <carousel />
    <h2>The above is carousel component</h2>

    <autoCarousel />
    <h2>The above is auto-carousel component</h2>
  </div>

</template>


