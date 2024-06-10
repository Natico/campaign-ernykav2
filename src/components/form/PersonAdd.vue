<template>
    <a-form :model="formState" name="basic" autocomplete="off" @finish="onFinish" @finishFailed="onFinishFailed">

        <h3>اطلاعات فرم زیر را تکمیل کنید</h3>
        <p class="modal-des">نام کاربری از قسمت اطلاعات هویتی، امنیت حساب قابل مشاهده می‌باشد</p>

        <a-form-item name="username">
            <a-input v-model:value="formState.username" class="user-input" placeholder="نام کاربری" />
        </a-form-item>

        <a-form-item>
            <a-button html-type="submit" class="join-campaign-btn" type="primary">شرکت در کمپین</a-button>
        </a-form-item>
    </a-form>
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
import { reactive } from 'vue';
const formState = reactive({
    username: '',
});
const onFinish = values => {
    console.log('Success:', values);
};
const onFinishFailed = errorInfo => {
    console.log('Failed:', errorInfo);
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
</style>