<template>
    <a-button type="primary" @click="openNotification">Open the notification box</a-button>
  </template>
  <script setup>
  import { notification } from 'ant-design-vue';
  const openNotification = () => {
    notification.open({
      message: 'Notification Title',
      description:
        'I will never close automatically. I will be close automatically. I will never close automatically.',
      duration: 0,
    });
  };
  </script>