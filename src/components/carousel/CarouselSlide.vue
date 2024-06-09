<template>
    <Carousel v-bind="settings" :breakpoints="breakpoints">
        <Slide :key="1">
            <div class="carousel__item">
                <img class="coin-img bitcoin" src="../../assets/img/suunto9-v2.png" alt="" />
                <img class="coin-img bitcoin deactive" src="../../assets/img/suunto9-deactive-v2.png" alt="" />
                <span>ساعت هوشمند سونتو SUUNTO 9 PEAK All Black Titanium</span>
            </div>
        </Slide>
        <Slide :key="2">
            <div class="carousel__item">
                <img class="coin-img bitcoin" src="../../assets/img/wh-1000xm5-v2.png" alt="" />
                <img class="coin-img bitcoin deactive" src="../../assets/img/wh-1000xm5-deactive-v2.png" alt="" />
                <span>هدفون بلوتوثی سونی مدل 2023 WH-1000XM5</span>
            </div>
        </Slide>
        <Slide :key="3">
            <div class="carousel__item">
                <img class="coin-img bitcoin" src="../../assets/img/galaxy-Z-v2.png" alt="" />
                <img class="coin-img bitcoin deactive" src="../../assets/img/galaxy-Z-deactive-v2.png" alt="" />
                <span>Galaxy Z Fold 5 گوشی</span>
            </div>
        </Slide>
        <template #addons>
            <Pagination />
            <Navigation />
        </template>
    </Carousel>

</template>

<script>
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide, Pagination } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({

    components: {
        Carousel,
        Slide,
        Pagination,
        Navigation,
    },
    data: () => ({
        // carousel settings
        settings: {
            wrapAround: true,
            itemsToScroll: 1,
            snapAlign: 'center',
        },
        // breakpoints are mobile first
        // any settings not specified will fallback to the carousel settings
        breakpoints: {
            // 700px and up
            700: {
                itemsToShow: 1,
                snapAlign: 'center',
            },
            // 1024 and up
            1024: {

                itemsToShow: 3,
                snapAlign: 'center',
            },
        },
    }),
})
</script>

<style scoped lang="scss">
.carousel {
    margin-top: 100px;
    ;
    // min-height: 400px;

    .carousel__viewport {

        height: 300px;
    }

    @media (max-width : 576px) {
        margin-top: 50px;
        ;

    }
}

.carousel__item {
    width: 312px;
    height: 340px;
    margin-top: 50px;

    // border: 1px solid red;
    @media (max-width : 576px) {
        margin-top: 0;


    }

    img {
        width: inherit;

       

        &:not(.deactive) {
            display: none;
        }
    }

    span {
        color: var(--Excoino-SSR-primaryText, #0F0E14);
        text-align: center;
        font-family: IRANSansX;
        font-size: 16px;
        font-style: normal;
        font-weight: 600;
        line-height: 40px;

        /* 250% */
        @media (max-width : 576px) {
            color: var(--Excoino-SSR-primaryText, #0F0E14);
            text-align: center;
            font-family: IRANSansX;
            font-size: 12px;
            font-style: normal;
            font-weight: 600;
            line-height: 21.214px;
            /* 250% */

        }
    }

    @media (max-width : 576px) {
        width: 165px;
        height: 180px;

    }

}

.carousel__slide {
    padding: 5px;
}

.carousel__viewport {
    perspective: 3000px;
    height: 300px;
}

.carousel__track {
    transform-style: preserve-3d;
}

.carousel__slide--sliding {
    transition: 0.5s;
}

.carousel__slide {
    opacity: 0.9;
    transform: rotateY(-30deg) scale(0.7);
}

.carousel__slide--active~.carousel__slide {
    transform: rotateY(20deg) scale(0.9);
}

.carousel__slide--prev {
    opacity: 0.5;
    transform: rotateY(-0deg) scale(0.7) translateY(-50px) !important;
}

.carousel__slide--next {
    opacity: 0.5;
    transform: rotateY(30deg) scale(0.7) translateY(-50px) !important;
}

.carousel__slide--active {
    opacity: 1;
    transform: rotateY(0) scale(1.1);

    @media (max-width : 576px) {
        transform: rotateY(0) scale(1);

    }

    img {
        &:not(.deactive) {
            transition: all 400ms;
            display: block !important;
        }

        &.deactive {
            transition: all 400ms;
            display: none;
        }
    }
}
</style>
