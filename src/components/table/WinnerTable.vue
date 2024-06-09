<template>
  <div id="table" class="container">
    <div class="head">
      <span>جدول نفرات برتر </span>
      <IconCup />
    </div>
    <!-- table head -->
    <div id="thead">
      <div class="rank">رتبه</div>
      <div class="name">نام کاربر</div>
      <div class="score">امتیاز</div>
    </div>
    <!-- end -->
    <section class="container-cart">
      <TableRow :rank="1" username="moh****7869" score_with_referral="923200" />
      <TableRow
        :rank="Number(2)"
        :username="data.find((item) => item.rank === '1')?.username"
        :score_with_referral="data.find((item) => item.rank === '1')?.score"
      />
      <TableRow :rank="Number(3)" username="ari****re12" score_with_referral="526002" />
      <TableRow :rank="Number(4)" username="sam****3693" score_with_referral="413450" />
      <TableRow
        v-for="(item, index) in data.slice(1, 7)"
        :key="index"
        :rank="+item.rank + 3"
        :username="item.username"
        :score_with_referral="item.score"
      />
    </section>
  </div>
</template>
<script>
import TableRow from './TableRow.vue'

export default {
  data() {
    return {
      data: []
    }
  },
  mounted() {
    this.getData()
  },
  methods: {
    getData() {
      fetch('https://api-marketing.excoino.net/board/get/json', {
        method: 'GET',
        headers: {
          'Content-Type': 'application/json',
          'P-API-KEY': '84fa8361-e610-56f5-2aea-b57564e0834c'
        }
      })
        .then((res) => res.json())
        .then((data) => {
          this.data = data.slice(0, 10)
        })
    }
  },
  components: { TableRow }
}
</script>

<script setup>
import IconCup from '../icons/IconCup.vue'
</script>

<style lang="scss" scoped>
#table {
  background: url('../../assets/img/background-liner-bid.png') no-repeat;

  width: 100%;
  max-width: 1280px;
  min-height: 1088px;

  margin-bottom: 500px;
  padding-top: 100px;
  padding-bottom: 32px;
  display: flex;
  flex-direction: column;
  // align-items: center;
  // justify-content: center;

  @media (max-width:576px) {
    margin-bottom: 0px;
    
  }

  .head {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding-bottom: 32px;

    span {
      color: var(--Excoino-SSR-primary, #2354e7);
      text-align: center;
      font-family: IRANSansX;
      font-size: 20px;
      font-style: normal;
      font-weight: 700;
      line-height: 40px;
      /* 200% */
    }
  }

  .container-cart {
    display: grid;
    gap: 8px;
    width: 100%;
  }

  #thead {
    width: 100%;
    height: 54px;
    border-radius: 8px;
    background: var(--Excoino-SSR-pureWhite, #fff);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 32px;
    margin-bottom: 24px;
    color: var(--Excoino-SSR-primary, #2354e7);
    text-align: center;
    /* Body/Medium */
    font-family: IRANSansX;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 24px;
    /* 171.429% */

    .rank {
      flex: 1;
      text-align: start;
    }

    .name {
      flex: 1;
    }

    .score {
      flex: 3;
      text-align: end;
    }
  }

  @media screen and (max-width: 768px) {
    #thead {
      // width: 328px;
    }
  }
}
</style>
