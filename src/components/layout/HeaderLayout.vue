<script setup>
import IconExcoino from '../icons/IconExcoino.vue'
import JoinCampaingnBtn from '../joinToCampaign/JoinButton.vue'
import CarouselSlide from '../carousel/CarouselSlide.vue'
</script>

<!-- <script>
import { Carousel3d, Slide } from 'vue-carousel-3d';

export default {

  components: {
    Carousel3d,
    Slide
  }

};
</script> -->

<template>
    <header class="container">
        <a-flex :justify="'center'" class="comtainer">
            <img class="coin-img bitcoin" src="../../assets/img/bitcoin.png" alt="" />
            <img class="coin-img solana" src="../../assets/img/solana.png" alt="" />
            <IconExcoino class="excoino-logo" />
        </a-flex>
        <a-flex :justify="'center'">
            <h1>گنجینو</h1>
        </a-flex>
        <a-flex :justify="'center'">
            <h2>سرمایه‌های اندک‌، بردهای بزرگ</h2>
        </a-flex>
        <a-flex :justify="'center'">
            <p class="header-des">
                با ورود سرمایه به اکسکوینو امتیاز بگیر و شانست رو برای بردن جوایز ارزنده کمپین افزایش بده
            </p>
        </a-flex>
        <JoinCampaingnBtn class="header-join" :justify="'center'" />

        <CarouselSlide />
    </header>
</template>

<style scoped lang="scss">
header {
    position: relative;
    max-width: 1000px;
}

.excoino-logo {
    margin-top: 104px;
    margin-bottom: 24px;
}

h1 {
    color: var(--Excoino-SSR-primary, #2354e7);
    text-align: center;
    /* Large Headline/Bold */
    font-family: IRANSansX;
    font-size: 48px;
    font-style: normal;
    font-weight: 800;
    line-height: 76px;

    /* 158.333% */
    @media(max-width : 768px) {
        font-size: 32px;
        font-style: normal;
        font-weight: 500;
        line-height: 48px;
        /* 150% */
    }
}

h2 {
    color: var(--label-primary, #0f0e14);
    text-align: center;
    /* Small Headline/Medium */
    font-family: IRANSansX;
    font-size: 28px;
    font-style: normal;
    font-weight: 500;
    line-height: 44px;

    /* 157.143% */

    @media(max-width : 768px) {
        font-size: 16px;
        font-style: normal;
        font-weight: 500;
        line-height: 24px;
        /* 150% */
    }
}

.header-des {
    color: var(--label-primary, #0f0e14);
    text-align: center;
    /* Small Title/Reg */
    font-family: IRANSansX;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 28px;

    /* 155.556% */
    @media(max-width : 768px) {
        font-family: IRANSansX;
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 24px;
        /* 171.429% */
    }
}

.coin-img {
    position: absolute;
    top: 104px;

    &.bitcoin {
        right: 0;
    }

    &.solana {
        left: 0;
    }

    @media (max-width : 576px) {
        display: none;

    }
}

.header-join{
    @media (max-width : 576px) {
        display: none;

    }
}
</style>
