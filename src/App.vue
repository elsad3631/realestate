<script setup lang="ts">
import { RouterView } from 'vue-router'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import Footer2 from '@/components/Footer2.vue'
import Header2 from './components/Header2.vue'
import Footer3 from './components/Footer3.vue'
import ScrollTop from './elements/ScrollTop.vue'
import Cursor from './elements/Cursor.vue'
</script>

<template>
  <div class="page-wraper">
    <Cursor />
    <component :is="$route.meta.layout">
      <ScrollTop />
      <Header />
      <RouterView />
      <Footer />
    </component>
    <component :is="$route.meta.layout2">
      <ScrollTop />
      <Header />
      <RouterView />
      <Footer2 />
    </component>
    <component :is="$route.meta.layout3">
      <ScrollTop />
      <Header2 />
      <RouterView />
      <Footer3 />
    </component>
    <component :is="$route.meta.layout4">
      <RouterView />
    </component>
  </div>
</template>
