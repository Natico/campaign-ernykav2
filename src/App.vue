<script setup>
// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
import FooterLayout from './components/layout/FooterLayout.vue'
import HeaderLayout from './components/layout/HeaderLayout.vue'
import ContentLayout from './components/layout/ContentLayout.vue'

import enUS from 'ant-design-vue/es/locale/en_US' // enUS
import faIR from 'ant-design-vue/es/locale/fa_IR' // faIR

import { reactive, ref } from 'vue'
const state = reactive({
  direction: 'rtl'
})
const locale = ref(faIR.locale)
</script>

<template>
  <a-config-provider :direction="state.direction" :locale="locale === 'en' ? enUS : faIR">
    <a-layout style="background-color: transparent">
      <HeaderLayout />
      <ContentLayout />
      <FooterLayout />
    </a-layout>
  </a-config-provider>
</template>

<style>
/* @import "font.css"; */

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  font-family: IRANSansX !important;
}

body,
html {
  background: linear-gradient(
    180deg,
    #e6f1fc 0.14%,
    rgba(255, 255, 255, 0.9) 33.89%,
    #c7e3ff 65.33%,
    #e8f3ff 110.84%,
    rgba(35, 84, 231, 0.3) 127.62%
  );
  font-family: IRANSansX;
}

input,
button,
textarea {
  font-family: inherit;
}

a {
  cursor: pointer;
  text-decoration: none;
  color: inherit;
}

.container {
  max-width: 1280px;
  margin-inline: auto;
}

.container {
  position: relative;
  margin-left: auto;
  margin-right: auto;
  padding-right: 15px;
  padding-left: 15px;
}
@media (min-width: 476px) {
  .container {
    padding-right: 15px;
    padding-left: 15px;
  }
}
@media (min-width: 768px) {
  .container {
    padding-right: 15px;
    padding-left: 15px;
  }
}
@media (min-width: 992px) {
  .container {
    padding-right: 15px;
    padding-left: 15px;
  }
}
@media (min-width: 1200px) {
  .container {
    padding-right: 15px;
    padding-left: 15px;
  }
}
@media (min-width: 476px) {
  .container {
    width: 100%;
  }
}
@media (max-width: 476px) {
  .container {
    width: 100%;
  }
} 
@media (min-width: 768px) {
  .container {
    width: 720px;
    max-width: 100%;
  }
}
@media (min-width: 992px) {
  .container {
    width: 960px;
    max-width: 100%;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
    max-width: 100%;
  }
}
@media (min-width: 1400px) {
  .container {
    width: 1340px;
    max-width: 100%;
  }
}
</style>
