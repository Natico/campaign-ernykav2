<template>
  <vue-countdown class="counter" :time="time" v-slot="{ days, hours, minutes, seconds }">
    <div class="box">
      <span class="time">{{ days }}</span>
      <span class="name">روز</span>
    </div>
    <div class="box">
      <span class="time">{{ hours }}</span>
      <span class="name">ساعت</span>
    </div>
    <div class="box">
      <span class="time">{{ minutes }}</span>
      <span class="name">دقیقه</span>
    </div>
    <div class="box">
      <span class="time">{{ seconds }}</span>
      <span class="name">ثانیه</span>
    </div>
  </vue-countdown>
</template>

<script setup>
import VueCountdown from '@chenfengyuan/vue-countdown'
</script>

<style scoped lang="scss">
.counter {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin: 32px 0 56px 0;
  direction: ltr;

  .box {
    padding: 8px 12px;
    justify-content: center;
    align-items: center;
    display: flex;
    flex-direction: column;
    border-radius: 4.483px;
    border: 0.747px solid var(--Excoino-SSR-border, #b7b9cb);
    max-width: 50px;
    min-width: 50px;
    max-height: 63px;
    min-height: 63px;
    color: var(--Excoino-SSR-primaryText, #0f0e14);
    font-size: 24px;
    font-style: normal;
    font-weight: 700;

    .name {
      color: var(--Excoino-SSR-secondaryText, #817e8c);
      font-size: 14.942px;
      font-style: normal;
      font-weight: 400;
      line-height: 23.907px;
    }
  }
}
</style>
