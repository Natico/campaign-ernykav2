<template>
  <div id="row">
    <div class="rank">
      <!-- <svg
        xmlns="http://www.w3.org/2000/svg"
        width="32"
        height="32"
        viewBox="0 0 22 24"
        fill="none"
        class="svg"
      >
        <path d="M11 0L21.3923 6V18L11 24L0.607696 18V6L11 0Z" fill="#2E2F49" />
      </svg> -->
      <div class="parent">
        <span class="text">
          {{ rank }}
        </span>
      </div>
    </div>
    <div class="name">{{ username }}</div>
    <!-- <div class="score">{{ score_with_referral | e2p }}</div> -->
    <div class="score">{{ score_with_referral }}</div>
  </div>
</template>
<script>
export default {
  data() {
    return {}
  },
  props: {
    rank: Number,
    username: String,
    score_with_referral: String,
    reset: Boolean
  },
  computed: {
    e2p: () => {
      const e2p = (s) => s.toString().replace(/\d/g, (d) => '۰۱۲۳۴۵۶۷۸۹'[d])
      const seperatedNumber = this.score_with_referral
        .toString()
        .match(/(\d+?)(?=(\d{3})+(?!\d)|$)/g)
      const joinedNumber = seperatedNumber.join(',')
      return e2p(joinedNumber)
    }
  }
}
</script>
<style lang="scss" scoped>
#row {
  width: 100%;
  height: 54px;
  border-radius: 8px;
  background: var(--Excoino-SSR-pureWhite, #fff);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 32px;
  color: var(--Excoino-SSR-primary, #2354e7);
  text-align: center;
  font-family: IRANSansWebFaNum;
  font-size: 14px;
  font-style: normal;
  font-weight: 700;
  line-height: 29.884px;

  /* 213.455% */
  .rank {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    color: var(--Excoino-SSR-primary, #2354e7);
    font-size: 15px;

    font-weight: 700;
    z-index: 1;
    flex: 1;
    position: relative;

    .parent {
      width: 25px;
      height: 25px;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='22' height='24' viewBox='0 0 22 24' fill='none'%3E%3Cpath d='M11 0L21.3923 6V18L11 24L0.607696 18V6L11 0Z' fill='%231A8CFF' fill-opacity='0.16'/%3E%3C/svg%3E");
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      display: flex;
      align-items: center;
      justify-content: center;
      line-height: 25px;

      .text {
        margin-top: 2px;
      }
    }
  }

  .name {
    color: var(--Excoino-SSR-primaryText, #0f0e14);
    font-size: 14px;

    font-weight: 500;
    text-align: right;
    flex: 4.3;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  }

  .score {
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: left;
    max-width: fit-content;
    max-height: 28px;
    border-radius: 8px;
    background: #2354e7;
    color: var(--Excoino-SSR-pureWhite, #fff);
    font-size: 16px;
    font-weight: 700;
    flex: 3;
    line-height: 28px;
    padding: 0 8px;
  }

  &:first-child {
    background: var(--Excoino-SSR-primary, #2354e7);

    .rank,
    .name {
      color: #fff;
    }

    .score {
      background: var(--Excoino-SSR-semanticLight2, rgba(26, 140, 255, 0.16));
    }
  }
}

@media screen and (max-width: 768px) {
  #card {
    // width: 328px;
    // .rank {
    //   flex: 1;
    // }
    // .name {
    //   flex: 1;
    // }
    // .score {
    //   flex: 1;
    // }
  }
}
</style>
