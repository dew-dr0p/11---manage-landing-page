<template>
    <img src="../assets//images/bg-tablet-pattern.svg" alt="" class="absolute -right-40 -top-40 -z-50">
    <div class="flex my-20 justify-between items-center">
        <img src="../assets/images/logo.svg" alt="Manage Logo">
        <div class="flex gap-10 text-primary-DarkBlue cursor-pointer">
            <p>Pricing</p>
            <p>Products</p>
            <p>About Us</p>
            <p>Careers</p>
            <p>Community</p>
        </div>
        <MainButton text="Get Started" />
    </div>
</template>

<script setup lang="ts">
import MainButton from './MainButton.vue';
</script>