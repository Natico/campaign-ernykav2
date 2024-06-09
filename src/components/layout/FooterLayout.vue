<script setup>
import IconInstagram from '../icons/IconInstagram.vue'
import IconLinkedin from '../icons/IconLinkedin.vue'
import IconeAparat from '../icons/IconeAparat.vue'
import IconeTwitter from '../icons/IconeTwitter.vue'
import IconeTelegram from '../icons/IconeTelegram.vue'
</script>

<template>
  <footer id="footer">
    <div class="social">
      <a href="https://instagram.com/excoino_com?igshid=NzZhOTFlYzFmZQ==" target="_blank">
        <IconInstagram />
      </a>
      <a href="https://t.me/excoino" target="_blank">
        <IconeTelegram />
      </a>
      <a href="http://aparat.com/excoino/" target="_blank">
        <IconeAparat />
      </a>
      <a href="https://twitter.com/excoino" target="_blank">
        <IconeTwitter />
      </a>
      <a href="https://ir.linkedin.com/company/excoino-com" target="_blank">
        <IconLinkedin />
      </a>
    </div>
    <div class="links">
      <a-flex>
        <a href="https://www.excoino.com/">صفحه اصلی</a>
        <a href="https://www.excoino.com/terms-of-service/">قوانین استفاده</a>
        <a href="https://www.excoino.com/privacy-policy/">حفظ حریم خصوصی</a>
        <a href="https://www.excoino.com/about-us/">درباره‌ی ما</a>
        <a href="https://www.excoino.com/contact/">تماس باما</a>
      </a-flex>
    </div>
  </footer>
</template>

<style scoped lang="scss">
#footer {
  background: var(--Excoino-SSR-pureWhite, #fff);
  display: flex;
  // width: 1281px;
  padding: 16px 120px;
  flex-direction: column;
  align-items: center;

  @media (max-width:576px) {
    display: none;
    
  }

  .social {
    a {
      width: 24px;
      height: 24px;
      margin-inline-end: 24px;
      display: inline-block;
    }
    margin-bottom: 16px;
  }

  .links {
    a {
      color: var(--Excoino-SSR-secondaryText, #817e8c);
      text-align: center;
      // font-family: Vazirmatn;
      font-size: 12px;
      font-style: normal;
      font-weight: 400;
      line-height: 20px;
      /* 166.667% */
      margin-inline-end: 16px;
      height: 20px;
      &:hover {
        color: #000;
        font-weight: 500;
      }
    }
  }

  a {
    font-family: IRANSansX;

    svg {
      // fill : #2354E7
      stroke: #2354e7;
    }
  }
}
</style>
