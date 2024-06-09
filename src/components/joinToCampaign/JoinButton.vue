<template>
  <a-flex :justify="justify">
    <a @click="showModal">
      <button class="CTA btn" id="CTA">شرکت در کمپین</button>
    </a>
    <!-- <a-button type="primary" @click="showModal">Open Modal</a-button> -->
    <a-modal class="join-info-modal" v-model:open="open" :footer="null">
      <h3>اطلاعات فرم زیر را تکمیل کنید</h3>
      <p class="modal-des">نام کاربری از قسمت اطلاعات هویتی، امنیت حساب قابل مشاهده می‌باشد</p>
      <a-input class="user-input" v-model:value="value" placeholder="نام کاربری" />
      <a-button class="join-campaign-btn" type="primary">شرکت در کمپین</a-button>


    </a-modal>
  </a-flex>
</template>

<script setup>
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
.join-info-modal {
  .join-campaign-btn {
    margin-top: 112px;
    text-align: center;
    height: 45px;
    padding: 8px 24px;
    border-radius: 8px;
    background: var(--Temp-Pri, #500FE9);
    width: 100%;
    color: var(--Text-Light-Chrysler-Blue-98, #FAF9FA);
    /* Body/Medium */
    font-family: IRANSansX;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 24px;
    /* 171.429% */
  }

  .user-input {
    height: 56px;
    padding: 16px;
  }

  h3 {
    color: var(--Text-Dark-Chrysler-Blue-8, #131217);
    text-align: right;
    /* Title/Reg */
    font-family: IRANSansX;
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: 32px;

    /* 160% */
    @media (max-width:576px) {
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: 24px;
      /* 150% */
    }
  }

  p.modal-des {
    color: var(--Text-Dark-Chrysler-Blue-36, #595463);
    text-align: right;
    font-family: Vazirmatn;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 24px;

    /* 150% */
    @media (max-width:576px) {
      font-size: 14px;
      font-style: normal;
      font-weight: 400;
      line-height: 24px;
      /* 171.429% */
    }
  }
}

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
