<template>
    <a-form ref="formRef" :model="formState" name="addPerson" autocomplete="off" :rules="rules" @finish="onFinish"
        @finishFailed="onFinishFailed">

        <h3>اطلاعات فرم زیر را تکمیل کنید</h3>
        <p class="modal-des">نام کاربری از قسمت اطلاعات هویتی، امنیت حساب قابل مشاهده می‌باشد</p>

        <a-form-item name="username">
            <a-input v-model:value="formState.username" class="user-input" placeholder="نام کاربری" />
        </a-form-item>

        <a-form-item>
            <a-button class="join-campaign-btn" type="primary" @click.prevent="onSubmit" :loading="loading">شرکت در کمپین</a-button>
        </a-form-item>
    </a-form>
</template>

<script setup>
import { notification } from 'ant-design-vue';
import { reactive, ref } from 'vue';

const formState = reactive({
    username: '',
});
const formRef = ref();
const loading = ref(false);
const rules = {
    username: [
        {
            required: true,
            message: 'لطفا نام کاربری را وارد کنید',
            trigger: 'change',
        }
    ],
};
const onFinish = values => {
    console.log('Success:', values);
};
const onFinishFailed = errorInfo => {
    console.log('Failed:', errorInfo);
};
const onSubmit = () => {
    loading.value = true;
    formRef.value.validate()
        .then(() => {
            const dataObj = {
                job: formState.username,
                firstName: 'treasuryFn',
                lastName: 'treasuryLn',
                phoneNumber: "09120000000",
                email: "treasury@ernyka.com",
                type: "treasury",
            }
            console.log(dataObj);
            fetch("https://api-marketing.excoino.net/person/add", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                    "P-API-KEY": "81fa05a2-6e67-44c4-b072-7952aa052e07",
                },
                body: JSON.stringify(dataObj),
            })
                .then((res) => res.json())
                .then((data) => {
                    loading.value = false;
                    if (data.status === 201 || data.status === 200) {
                        notification.open({
                            description: "اطلاعات شما با موفقیت ثبت شد",
                            duration: 100,
                        });

                    } else if (data.status === 500) {
                        notification.open({
                            description: "اطلاعات شما قبلا ثبت شده است",
                            duration: 100,
                        });

                    } else {
                        notification.open({
                            description: "مشکلی در سرور وجود دارد لطفا مجدد امتحان کنید",
                            duration: 100,
                        });
                    }
                });

        })
        .catch(error => {
            console.log('error', error);
        });


    console.log('submit:');
    onFinish();
    onFinishFailed();
}
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
        &[disabled] {
            background: var(--Temp-Pri, #737373);
        }
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