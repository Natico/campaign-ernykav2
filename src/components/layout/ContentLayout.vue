<template>
  <main class="">
    <a-row class="rules-section container">
      <a-col class="title" :span="24">قوانین و نحوهٔ شرکت در کمپین</a-col>

      <a-col :xs="24" :md="18">
        <a-row>
          <a-col :xs="24" :md="8">
            <RulesCard
              :title="'ثبت نام'"
              :description="'روی گزینهٔ شرکت در کمپین کلیک کنید و اطلاعات خودتون رو وارد کنید.'"
            />
          </a-col>
          <a-col :xs="24" :md="8">
            <RulesCard
              :title="'کسب امتیازات'"
              :description="'به ازای هر ۱۰۰ دلار واریزی ۲ امتیاز کسب می‌کنید'"
            />
          </a-col>
          <a-col :xs="24" :md="8">
            <RulesCard
              :title="'کسر امتیازات'"
              :description="'به ازای هر ۱۰۰ دلار خروج، ۴ امتیاز از دست می‌دهید'"
            />
          </a-col>
        </a-row>
        <a-row>
          <a-col :xs="24" :md="8">
            <RulesCard
              :title="'کسر امتیاز از دوستان'"
              :description="'به ازای هر ۱۰۰ دلار خروج کاربری که دعوت کرده‌اید، ۲ امتیاز از دست می‌دهید'"
            />
          </a-col>
          <a-col :xs="24" :md="16">
            <RulesCard
              class="doble-width"
              :isIconExcoin="true"
              :title="'1درصد'"
              :description="'اگر در طول دورهٔ کمپین هیچ خروج سرمایه‌ای نداشته باشید، ۱ درصد از کل سرمایه ورودی‌تان را به شکل کش‌بک از اکسکوینو هدیه می‌گیرید.'"
            />
          </a-col>
        </a-row>
      </a-col>
      <a-col :xs="24" :md="6">
        <a-row style="height: 100%">
          <a-col :span="24">
            <RulesCard
              class="doble-height"
              :title="'کسب امتیاز از دوستان'"
              :description="'اگر کسی رو دعوت کنید، به ازای هر ۱۰۰ دلار واریزیِ کاربر دعوت شده، شما ۱ امتیاز می‌گیرید'"
            />
          </a-col>
        </a-row>
      </a-col>
    </a-row>
    <a-row>
      <a-col :span="24">
        <CountDownSection />
      </a-col>
    </a-row>
    <a-row>
      <a-col :span="24">
        <WinnerTable />
      </a-col>
    </a-row>
  </main>
</template>

<script setup>
import RulesCard from './RulesCard.vue'
import CountDownSection from '../countDownTimer/CountDownSection.vue'
import WinnerTable from '../table/WinnerTable.vue'
</script>

<style scoped lang="scss">
main {
  // width: 1280px;
  // margin: auto;
  background: transparent;
}

.rules-section {
  @media (max-width: 576px) {
      margin-top: 50px;
    
  }

  .title {
    color: var(--Excoino-SSR-primaryText, #0f0e14);
    text-align: right;
    // font-family: IRANSansWeb;
    font-size: 21.26px;
    font-style: normal;
    font-weight: 500;
    line-height: 33.522px;
    /* 157.681% */
    margin-bottom: 20px;
    
    @media (max-width: 576px) {
      display: none;
    }
  }

  .doble-height {
    height: calc(100% - 16px);
   
  }
}
</style>
