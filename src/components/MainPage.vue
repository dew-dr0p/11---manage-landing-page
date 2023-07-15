<template>
    <div class="grid grid-cols-2 gap-20 mb-20">
        <div class="max-w-lg">
            <h3 class="text-primary-DarkBlue font-bold text-6xl leading-[1.15] mb-10">Bring everyone together to build better products.</h3>
            <p class="text-lg max-w-sm mb-10">Manage makes it simple for software teams to plan day-to-day 
            tasks while keeping the larger team goals in view.</p>
            <MainButton text="Get Started" class="mb-5" />
        </div>
        <div>
            <img src="../assets/images/illustration-intro.svg" alt="">
        </div>
    </div>
    <div class="grid grid-cols-2 gap-20 my-20">
       <div class="max-w-lg">
        <h4 class="text-primary-DarkBlue font-bold text-[2.75rem] mb-10">What’s different about Manage?</h4>
        <p class="text-lg max-w-sm mb-10">
            Manage provides all the functionality your team needs, without 
            the complexity. Our software is tailor-made for modern digital 
            product teams.
        </p>
       </div>
       <div>
           <div v-for="benefit in benefits" :key="benefit.id" class="flex gap-5 mb-10">
            <button class="p-2 px-6 font-bold rounded-full text-secondary-LightGray bg-primary-BrightRed h-fit">{{ benefit.id }}</button>
            <div class="mt-2">
                <h6 class="font-bold mb-5 text-primary-DarkBlue">{{ benefit.title }}</h6>
                <p>{{ benefit.subtitle }}</p>
            </div>
           </div>
           <img src="../assets/images/bg-tablet-pattern.svg" alt="" class="absolute -z-50 -left-[30rem] -bottom-[90%]">
       </div>
    </div>
    <div class="text-center my-20">
        <h4 class="text-primary-DarkBlue font-bold text-[2.75rem] mb-32">What they’ve said</h4>
        <div class="grid grid-flow-col mb-16">
            <div class="max-w-lg p-10 bg-secondary-LightGray flex flex-col items-center">
                <img src="../assets/images/avatar-ali.png" alt="" class="relative -top-20 w-20">
                <h6 class="font-bold mb-5 text-primary-DarkBlue -mt-16">Ali Bravo</h6>
                <p>“We have been able to cancel so many other subscriptions since using 
                Manage. There is no more cross-channel confusion and everyone is much 
                more focused.”</p>
            </div>
            <div class="max-w-lg p-10 bg-secondary-LightGray flex flex-col items-center">
                <img src="../assets/images/avatar-ali.png" alt="" class="relative -top-20 w-20">
                <h6 class="font-bold mb-5 text-primary-DarkBlue -mt-16">Ali Bravo</h6>
                <p>“We have been able to cancel so many other subscriptions since using 
                Manage. There is no more cross-channel confusion and everyone is much 
                more focused.”</p>
            </div>
        </div>
        <MainButton text="Get Started"  class="mb-5"/>
    </div>
</template>

<script setup lang="ts">
import MainButton from './MainButton.vue';

const benefits = [
    {
        id: '01',
        title: 'Track company-wide progress',
        subtitle: 'See how your day-to-day tasks fit into the wider vision. Go from tracking progress at the milestone level all the way done to the smallest of details. Never lose sight of the bigger picture again.'
    },
    {
        id: '02',
        title: 'Advanced built-in reports',
        subtitle: 'Set internal delivery estimates and track progress toward company goals. Our customisable dashboard helps you build out the reports you need to keep key stakeholders informed.'
    },
    {
        id: '03',
        title: 'Everything you need in one place',
        subtitle: 'Stop jumping from one service to another to communicate, store files, track tasks and share documents. Manage offers an all-in-one team productivity solution.'
    }
]
</script>