<template>
    <section class="js-horizontal-collapse  horizontal-collapse">
      <ul class="horizontal-collapse__inner">
        <HorizontalCollapseItem v-for="(item, index) in items"  :key="index" :item="item" :index="index" :isActive="index === activeIndex" :color="item.color" @click="activeIndex = index" />
      </ul>
    </section>
  </template>
  
  <script setup>
  import HorizontalCollapseItem from "./HorizontalCollapseItem.vue";
  import {ref} from 'vue';
  const activeIndex = ref(0);
  const items = [
    {
        icon: `<img src="src/assets/images/Profile.png" alt="">`,
        content: `
            <div class="horizontal-collapse__body py-[5%] px-[15%] flex justify-center items-center gap-[150px] overflow-hidden">
             <img src="src/assets/images/me.png" alt="me" width="455px" height="640px">
             <div class="w-fit">
              <div class="w-fit">
                <h1><strong>Abdulla Yerezhep</strong></h1>
                <h1 class="mt-2 font-thin">UX/UI Designer & Fullstack Developer</h1>
              </div>
              <div class="mt-10">
                <h1 class="font-bold">About me</h1>
                <p class="mt-12 text-lg">Hello there! I'm Abdulla, a 24-year-old tech enthusiast from the beautiful country of Kazakhstan. I wear multiple hats in the world of technology, serving as both a creative UX/UI Designer and a proficient Fullstack Developer.<br><br>
                  My journey in the realm of software creation is fueled by a burning passion. I thrive on the art of designing user experiences that are not only visually appealing but also incredibly intuitive. On the other side of the spectrum, I dive deep into coding to construct powerful, efficient, and feature-rich applications.<br><br>
                  My portfolio showcases the results of this passion—a collection of projects that reflect my dedication to pushing the boundaries of what's possible in the world of technology. Explore my work and discover how I blend creativity with functionality to create software that makes a difference.
                  Welcome to my digital world of innovation and design! 🚀</p>
                <button class="mt-12 bg-white text-black">Contact me</button>
                </div>
              </div>
            </div>`,
            color: '#7DCE94'
    },
 
    {
        icon: `<img src="src/assets/images/Work.png" alt="">`,
        content: `<div class="w-full horizontal-collapse__body flex flex-col items-center py-5 px-14 text-[#393939]">
            <h1 class="font-bold">Design Projects</h1>
            <div class="flex justify-between">
              <div class="flex w-[30%] mt-10">
                  <div class="flex flex-col justify-start gap-2">
                    <img src="src/assets/images/project1.png" alt="">
                    <h2>Construction Marketplace</h2>
                    <p>Mobile app for connecting construction workers with marketplace.</p>
                    <div class="flex gap-5 items-center">
                      <button class="text-white">Demo</button>
                      <a href="">GitHub Repo</a>
                    </div>
                  </div>
              </div>
              <div class="flex w-[30%] mt-10">
                  <div class=" flex flex-col justify-start gap-2">
                    <img src="src/assets/images/project1.png" alt="">
                    <h2>Construction Marketplace</h2>
                    <p>Mobile app for connecting construction workers with marketplace.</p>
                    <div class="flex gap-5 items-center">
                      <button class="text-white">Demo</button>
                      <a href="">GitHub Repo</a>
                    </div>
                  </div>
              </div>
              <div class="flex w-[30%] mt-10">
                  <div class="flex flex-col justify-start gap-2">
                    <img src="src/assets/images/project1.png" alt="">
                    <h2>Construction Marketplace</h2>
                    <p>Mobile app for connecting construction workers with marketplace.</p>
                    <div class="flex gap-5 items-center">
                      <button class="text-white">Demo</button>
                      <a href="">GitHub Repo</a>
                    </div>
                  </div>
              </div>
            </div>
            <div class="my-10 w-full h-[0.5px] bg-gray-500 opacity-[0.2]"></div>
            <h1 class="font-bold mt-5">Code Projects</h1>
            <div class="flex justify-between">
              <div class="flex w-[30%] mt-10">
                  <div class="flex flex-col justify-start gap-2">
                    <img src="src/assets/images/project1.png" alt="">
                    <h2>Construction Marketplace</h2>
                    <p>Mobile app for connecting construction workers with marketplace.</p>
                    <div class="flex gap-5 items-center">
                      <button class="text-white">Demo</button>
                      <a href="">GitHub Repo</a>
                    </div>
                  </div>
              </div>
              <div class="flex w-[30%] mt-10">
                  <div class=" flex flex-col justify-start gap-2">
                    <img src="src/assets/images/project1.png" alt="">
                    <h2>Construction Marketplace</h2>
                    <p>Mobile app for connecting construction workers with marketplace.</p>
                    <div class="flex gap-5 items-center">
                      <button class="text-white">Demo</button>
                      <a href="">GitHub Repo</a>
                    </div>
                  </div>
              </div>
              <div class="flex w-[30%] mt-10">
                  <div class="flex flex-col justify-start gap-2">
                    <img src="src/assets/images/project1.png" alt="">
                    <h2>Construction Marketplace</h2>
                    <p>Mobile app for connecting construction workers with marketplace.</p>
                    <div class="flex gap-5 items-center">
                      <button class="text-white">Demo</button>
                      <a href="">GitHub Repo</a>
                    </div>
                  </div>
              </div>
            </div>  
      </div>`,
        color:'white'
    },
    {
        icon: `<img width="30px" height="30px" src="src/assets/images/File.png" alt="">`,
        content: ` <div class="w-full horizontal-collapse__body flex flex-col items-center py-5 px-[10%] text-white relative">
          <button class="absolute right-0 top-0 bg-[#393939]"><img src="src/assets/images/download.png" alt=""></button>
          <h1 class="w-full font-bold text-start">Resume</h1>
          <div class="px-[20%] flex mt-14 w-full justify-around">
            <div class="text-start w-[50%]">
              <p class="font-bold text-xl">Experience</p>
            </div>
            <div class="flex flex-col gap-9 justify-center items-start w-[50%]">
              <div>
                <h2 class="font-bold text-xl">Frontend Developer, Resort Holiday</h2>
                <p class="text-gray-100 mt-5">Mar 2023 - Present</p>
                <p class="text-gray-100 mt-2">Designed and developed resort-holiday.com features and widgets.</p>
              </div>
              <div>
                <h2 class="font-bold text-xl">UI/UX Designer, Freelance </h2>
                <p class="text-gray-100 mt-5">Jan 2023 - Present</p>
                <ul class="text-gray-100 mt-2">
                  <li>Product and system design for a complex product</li>
                  <li>Designed both consumer and developer products</li>
                  <li>Responsible for maintaining design across iOS, Android, and web</li>
                </ul>
              </div>
            </div>
          </div>
          <div class="px-[20%] flex mt-14 w-full justify-around">
            <div class="text-start w-[50%]">
              <p class="font-bold text-xl">Education</p>
            </div>
            <div class="flex flex-col gap-9 justify-center items-start w-[50%]">
              <h2 class="font-bold text-xl">University of Information Technology and Management</h2>
              <p class="text-gray-100">IT, Programming</p>
            </div>
          </div>
          <div class="px-[20%] flex mt-14 w-full justify-around">
            <div class="text-start w-[50%]">
              <p class="font-bold text-xl">Languages</p>
            </div>
            <div class="flex gap-9 justify-start items-center w-[50%]">
              <span>English:  Advanced</span>|<span>Russian:  Fluent</span>|<span>Kazakh:  Native</span>
            </div>
          </div>
          <div class="px-[20%] flex mt-14 w-full justify-around">
            <div class="text-start w-[50%]">
              <p class="font-bold text-xl">Links</p>
            </div>
            <div class="flex gap-9 justify-start items-center w-[50%]">
              <span>GitHub</span>|<span>LinkedIn</span>
            </div>
          </div>
        </div>`,
        color: '#393939'
    },
  ]
  </script>
  
  <style lang="scss">
  $transitionDurationMs: 0.5s;
  
  .horizontal-collapse {
    width: 100%;
    margin: 0 auto;
    justify-content: center;
    color: #fff;
  
    *,
    *:before,
    *:after {
      box-sizing: border-box;
    }
  
    &__inner {
      padding: 0;
      margin: 0;
      display: flex;
      flex-direction: row;
    }
  
    &__item {
      height: 100vh;
      list-style: none;
      padding: 0;
      transition: width $transitionDurationMs;
  
  
      &.is-active {
        .horizontal-collapse__inactive-content {
          opacity: 0;
        }
        .horizontal-collapse__active-content {
          opacity: 1;

        }
      }
    }
  
    &__inactive-content {
      opacity: 1;
      transition: opacity $transitionDurationMs;
    }
  
    &__active-content {
      transition: opacity $transitionDurationMs;
      cursor: default;
    }
  
  
    &__link {
      display: inline-block;
      background-color: #fff;
      color: #333;
      text-decoration: none;
      line-height: 1;
      padding: 1rem 2rem;
      border-radius: 2rem;
      font-size: 1.7rem;
      font-weight: bold;
    }
  }
  </style>