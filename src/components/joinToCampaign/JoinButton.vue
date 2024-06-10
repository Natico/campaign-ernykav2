<template>
  <a-flex :justify="justify">

    <a @click="showModal">
      <button class="CTA btn" id="CTA">شرکت در کمپین</button>
    </a>

    <a-modal class="join-info-modal" v-model:open="open" :footer="null">
      <PersonAdd />
    </a-modal>

  </a-flex>
</template>

<script setup>
import PersonAdd from "../form/AddPerson.vue";
defineProps({
  justify: {
    type: String
  }
})
import { ref } from 'vue';
const open = ref(false);
const showModal = () => {
  open.value = true;
};
</script>

<style scoped lang="scss">
a {
  cursor: pointer;
  display: flex;
  width: 403px;
  height: 58px;
  padding: 0px 16px;
  justify-content: center;
  align-items: center;
  gap: 16px;
  flex-shrink: 0;
  border-radius: 8px;
  background: var(--Excoino-SSR-primary, #2354e7);

  color: var(--grey-pure-white, #fff);
  text-align: center;
  /* Small Title/Bold */
  // font-family: IRANSansX;
  font-size: 18px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
  /* 155.556% */

  /* Button Style */
  button {
    background: transparent;
    border: none;
    outline: none;
    cursor: pointer;
    // box-shadow: 0px 1px 0px 0px rgba(255, 255, 255, 0.30) inset, 0px -1px 0px 0px rgba(0, 0, 0, 0.10) inset, 0px 4px 8px 0px rgba(0, 0, 0, 0.05);
  }

  @media (max-width : 576px) {
    width: 270px;
    height: 40px;
    font-family: IRANSansX;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 24px;
    /* 150% */

  }
}
</style>
