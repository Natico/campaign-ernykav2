<template>
  <div id="how" class="">
    <span>نحوه تعیین برندگان</span>
    <div>
      <p>
        به نفر اول یک عدد گوشی Samsung Galaxy Z Fold 5 و از بین 10 نفر بعدی به دو نفر به قید قرعه یک
        عدد هدفون بلوتوثی سونی مدل 2023 WH-1000XM5 و یک عدد ساعت هوشمند سونتو SUUNTO 9 PEAK All
        Black Titanium اهدا می گردد
      </p>
    </div>
  </div>
</template>
<script></script>
<style lang="scss" scoped>
#how {
  position: relative;
  max-width: 863px;
  min-height: 131px;
  border-radius: 12px;
  border: 2px solid var(--system-light-primary, #b2b2ff);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 80px auto;

  @media(max-width:350px) {
    margin: auto 15px;

    span {
      background: #d5eaff !important;
    }
  }

  span {
    position: absolute;
    top: -12px;
    padding-inline: 60px;
    color: var(--Excoino-SSR-primary, #2354e7);
    background: red;
    text-align: right;
    /* Small Title/Bold */
    font-family: IRANSansX;
    font-size: 18px;
    font-style: normal;
    font-weight: 700;
    line-height: 28px;
    /* 155.556% */

    @media(max-width:350px) and (min-width: 235px) {
      background: #d5eaff !important;
    }

    @media(min-width:998px) {
      background: #feffff !important;
    }

    @media(max-width:998px) and (min-width: 768px) {
      background: #edf6fe !important;
    }
    @media(max-width:768px) and (min-width: 576px) {
      background: #cee6ff !important;
    }

    @media(max-width:576px) and (min-width: 350px) {
      background: #d1e8ff !important;
    }



  }

  p {
    padding: 38px 32px 22px 32px;
    margin-bottom: 0;
    color: var(--Excoino-SSR-primaryText, #0f0e14);
    text-align: center;
    /* Large Body/Medium */
    font-family: IRANSansX;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 24px;
    /* 150% */
  }
}

@media screen and (max-width: 768px) {
  #how {
    max-width: 330px;
    min-height: 131px;
  }
}
</style>
