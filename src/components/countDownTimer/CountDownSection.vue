<template>
  <div id="countDown" class="">
    <div class="head">
      <p class="title">فقط تا<span class="highlight"> 15 تیر</span></p>
      <p class="des">
        یادت باشه برای کسب امتیاز فقط تا ۲۲ اسفند فرصت داری چون برنده‌ ۲۳ اسفند مشخص می‌شه!
      </p>
    </div>

    <CountDownTimer :time="time" />
    <JoinCampaingnBtn class="count-down-join" :justify="'center'" />
    <HowBeWinners />

    <div class="end">
      <!-- <p class="first">تنها تا پایان آذر</p>
        <p class="sec">برای شرکت در کمپین فرصت داری!</p> -->
    </div>
    <!-- <img src="@/assets/CountDown/waterMelon.svg" alt="" class="waterMelon" /> -->
    <!-- <img src="@/assets/CountDown/phone.svg" alt="" class="phone" />
      <img src="@/assets/CountDown/redMotor.svg" alt="" class="redMotor" /> -->
  </div>
</template>
<script setup>
import CountDownTimer from '../countDownTimer/CountDownTimer.vue'
import JoinCampaingnBtn from '../joinToCampaign/JoinButton.vue'
import HowBeWinners from '../how/HowWinners.vue'
</script>

<script>
export default {
  data() {
    const now = new Date()
    const newDay = Date.parse('05 July 2024 00:00:00 GMT')
    return {
      time: newDay - now
    }
  }
}
</script>

<style lang="scss" scoped>
.count-down-join{
  @media (max-width: 576px) {
    position: fixed;
    bottom: 10px;
    margin: 0 auto;
    left: 0;
    right: 0;
    z-index: 1000;
  }
}

#countDown {
  position: relative;
  padding-top: 92px;
  text-align: center;

  .head {
    .title {
      color: var(--Excoino-SSR-primaryText, #0f0e14);
      font-size: 32px;
      font-style: normal;
      font-weight: 700;
      line-height: 28px;

      /* 87.5% */
      span {
        color: var(--Excoino-SSR-primary, #2354e7);
        font-size: 32px;
        font-style: normal;
        font-weight: 700;
        line-height: 28px;
      }

      margin-bottom: 0;
    }

    .des {
      color: var(--Excoino-SSR-primaryText, #0f0e14);
      padding-top: 21px;
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: 44px;
      /* 157.143% */
    }
  }

  @media screen and (max-width: 768px) {
    .head {
      padding-inline: 16px;

      .title {
        font-size: 24px;
      }

      .des {
        font-size: 14px;
        line-height: 24px;
      }
    }
  }

  .end {
    padding-top: 32px;
    color: #afacbf;
    /* Title/Bold */
    font-size: 20px;
    font-style: normal;
    font-weight: 700;
    line-height: 32px;

    /* 160% */

    .sec {
      font-size: 14px;
      font-style: normal;
      font-weight: 400;
      line-height: 24px;
      /* 171.429% */
    }
  }
}
</style>
