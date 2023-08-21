<template>
    <div class="grid lg:grid-cols-2 justify-items-center lg:justify-items-start lg:gap-14 xl:gap-20 lg:mb-16 xl:mb-20 lg:px-20 xl:px-40">
        <div class="lg:hidden">
            <img src="../assets/images/illustration-intro.svg" alt="" id="image" class="w-[45rem]">
        </div>
        <div class="max-w-lg box text-center lg:text-left flex flex-col items-center lg:items-start">
            <h3 class="text-primary-DarkBlue font-bold text-5xl md:text-6xl lg:text-5xl xl:text-6xl leading-snug lg:leading-[1.15] xl:leading-[1.15] mb-10">Bring everyone together to build better products.</h3>
            <p class="lg:text-lg md:text-2xl text-xl lg:max-w-sm mb-10">Manage makes it simple for software teams to plan day-to-day 
            tasks while keeping the larger team goals in view.</p>
            <MainButton text="Get Started" class="mb-5 drop" />
        </div>
        <div class="lg:block hidden">
            <img src="../assets/images/illustration-intro.svg" alt="" id="image">
        </div>
    </div>
    <div class="grid grid-flow-row lg:grid-cols-2 lg:gap-14 xl:gap-20 lg:my-16 xl:my-20 lg:px-20 xl:px-40 relative">
       <div class="max-w-lg box2 text-center lg:text-left m-auto w-full lg:my-0">
        <h4 class="text-primary-DarkBlue font-bold mt-40 text-4xl md:text-[2.75rem] lg:text-4xl xl:text-[2.75rem] mb-10">What’s different about Manage?</h4>
        <p class="lg:text-lg md:text-2xl text-xl lg:max-w-sm mb-10">
            Manage provides all the functionality your team needs, without 
            the complexity. Our software is tailor-made for modern digital 
            product teams.
        </p>
       </div>
       <div>
           <div v-for="benefit in benefits" :key="benefit.id" class="flex ml-5 lg:ml-0 lg:gap-5 mb-10">
            <button class="p-2 px-5 md:px-6 lg:px-5 xl:px-6 font-bold rounded-full text-secondary-LightGray bg-primary-BrightRed h-fit">{{ benefit.id }}</button>
            <div class="">
                <h6 class="font-bold mb-5 text-primary-DarkBlue lg:bg-inherit px-8 -ml-4 lg:ml-0 -z-[1] relative lg:static py-2 lg:p-0 bg-secondary-paleRed">{{ benefit.title }}</h6>
                <p class="-ml-16 lg:ml-0">{{ benefit.subtitle }}</p>
            </div>
           </div>
        </div>
        <img src="../assets/images/bg-tablet-pattern.svg" alt="" class="absolute -z-50 lg:-left-[30rem] lg:top-3/4 trigger -right-[40rem] -top-3/4">
    </div>
    <div class="text-center lg:my-16 xl:my-20 lg:px-20 xl:px-40">
        <h4 class="text-primary-DarkBlue font-bold mt-10 text-4xl md:text-[2.75rem] lg:text-4xl xl:text-[2.75rem] mb-32">What they’ve said</h4>
        <div class="grid grid-flow-col gap-10 mb-16" id="slider">
            <div v-for="testimonial in testimonials" :key="testimonial.name" class="w-[32rem] p-10 bg-secondary-LightGray flex flex-col items-center transition ease-linear">
                <img :src="testimonial.avatar" alt="" class="relative -top-20 w-20">
                <h6 class="font-bold mb-5 text-primary-DarkBlue -mt-16">{{ testimonial.name }}</h6>
                <p>{{ testimonial.testimony }}</p>
            </div>
        </div>
        <MainButton text="Get Started"  class="mb-5"/>
    </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import MainButton from './MainButton.vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
    gsap.from('.box', { x: -600, duration: 1.5 })
    gsap.from('#image', { scale: 0.5, duration: 1.5 })
    gsap.from('.drop', { y: -50, duration: 1, delay: 0.5, ease: 'bounce.out'})
    gsap.from('.box2', { y: -150, duration: 1.5, scrollTrigger: { trigger: '.box2' }})
    gsap.from('.trigger', { x: -200, y: 200, duration: 1.5, scrollTrigger: { trigger: '.trigger', scrub: true } })
    slideTestimonials()
})

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

const testimonials = [
    {
        avatar: 'src/assets/images/avatar-anisha.png',
        name: 'Anisha Li',
        testimony: '“Manage has supercharged our team’s workflow. The ability to maintain visibility on larger milestones at all times keeps everyone motivated.”'
    },
    {
        avatar: 'src/assets/images/avatar-ali.png',
        name: 'Ali Bravo',
        testimony: '“We have been able to cancel so many other subscriptions since using Manage. There is no more cross-channel confusion and everyone is much more focused.”'
    },
    {
        avatar: 'src/assets/images/avatar-richard.png',
        name: 'Richard Watts',
        testimony: '“Manage allows us to provide structure and process. It keeps us organized and focused. I can’t stop recommending them to everyone I talk to!”'
    },
    {
        avatar: 'src/assets/images/avatar-shanai.png',
        name: 'Shanai Gough',
        testimony: '“Their software allows us to track, manage and collaborate on our projects from anywhere. It keeps the whole team in-sync without being intrusive.”'
    }
]

const slideTestimonials = () => {
    let arr = <any>[]
    for (let i = 0; i < testimonials.length; i++) {
        arr.push(document.getElementById('slider')?.children.item(i))
    }
    console.log(arr)
    let i = 1
    setInterval(() => {
        // arr.forEach()
        arr.forEach((e: any) => {
            e.style.transform = `translateX(-${i * 50}%)`;
        });
        i < arr.length ? i++ : i = 0
    }, 2000)
}
</script>