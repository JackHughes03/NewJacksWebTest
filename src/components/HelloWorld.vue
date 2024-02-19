<script setup>
import { ref, onMounted } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/swiper-bundle.css';
import SwiperCore, { Pagination, Navigation } from 'swiper/core';

SwiperCore.use([Pagination, Navigation]);

onscroll = (event) => {
  const swiper = document.querySelector('.swipercontainer'),
  title = document.querySelector('.title'),
  headingtitle = document.querySelector('.title h1'),
  headingp = document.querySelector('.title p'),
  secondsection = document.querySelector('.secondsection'),
  secondsectionwrapper = document.querySelector('.secondsectionwrapper');
  
  if (window.scrollY > 100) {
    swiper.style.transform = 'translateX(1000px)';
    swiper.style.opacity = '0';
  } else {
    swiper.style.transform = 'translateX(0)';
    swiper.style.opacity = '1';
  }
  
  setTimeout(() => {
    if (window.scrollY > 100) {    
      title.style.top = '50px';
      title.style.position = 'fixed';
      headingtitle.innerHTML = 'Services I offer';
      headingp.innerHTML = 'From multi-page websites, to single page, I am trained in all!.';
      
      secondsection.style.opacity = '1';
    } else {
      title.style.top = '160px';
      title.style.position = 'absolute';
      headingtitle.innerHTML = 'Hand-coded Websites';
      headingp.innerHTML = 'Why settle for an average website when you have an exceptional idea? <br> Get a hand-coded website today!';
      
      secondsection.style.opacity = '0';
    }
  }, 500);
  
  // if element is in view
  const topLeftSlide = document.getElementById('top-right-slide'),
  topRightSlide = document.getElementById('top-left-slide'),
  bottomRightSlide = document.getElementById('bottom-right-slide'),
  bottomLeftSlide = document.getElementById('bottom-left-slide'),
  thirdsection = document.querySelector('.thirdsection');
  
  if (window.scrollY <= 100) {
    topLeftSlide.style.opacity = '0';
    topLeftSlide.style.transform = 'translateX(56px)';
    topRightSlide.style.opacity = '0';
    topRightSlide.style.transform = 'translateX(-56px)';
    bottomLeftSlide.style.opacity = '0';
    bottomLeftSlide.style.transform = 'translateX(-56px)';
    bottomRightSlide.style.opacity = '0';
    bottomRightSlide.style.transform = 'translateX(56px)';
  }
  
  if (secondsection.getBoundingClientRect().top + 800 < window.innerHeight) {
    title.style.transform = 'translateX(-1000px)';
  } else {
    title.style.transform = 'translateX(0px)';
  }
  if (thirdsection.getBoundingClientRect().top + 650 < window.innerHeight) {
    title.style.transform = 'translateX(0px)';
    
    headingtitle.innerHTML = 'My Portfolio';
    headingp.innerHTML = 'See some of my work!';
  }
  
  if (secondsectionwrapper.getBoundingClientRect().top + 300 < window.innerHeight) {
    topLeftSlide.style.opacity = '1';
    topLeftSlide.style.transform = 'translateX(0)';
  }
  if (secondsectionwrapper.getBoundingClientRect().top + 700 < window.innerHeight) {
    topRightSlide.style.opacity = '1';
    topRightSlide.style.transform = 'translateX(0)';
  }
  if (secondsectionwrapper.getBoundingClientRect().top + 1100 < window.innerHeight) {
    bottomLeftSlide.style.opacity = '1';
    bottomLeftSlide.style.transform = 'translateX(0)';
  }
  if (secondsectionwrapper.getBoundingClientRect().top + 1500 < window.innerHeight) {
    bottomRightSlide.style.opacity = '1';
    bottomRightSlide.style.transform = 'translateX(0)';
  }
  
  if (secondsectionwrapper.getBoundingClientRect().top + 2000 < window.innerHeight) {
    secondsection.style.position = 'unset';
    secondsection.style.left = 'unset';
    secondsection.style.top = 'unset';
    secondsection.style.transform = 'unset';
    secondsectionwrapper.style.display = 'none';
  }
  
  const secondswiper = document.querySelector('.secondswiper');
  
  if (secondswiper.getBoundingClientRect().top + 200 < window.innerHeight) {
    secondswiper.style.opacity = '1';
  } else {
    secondswiper.style.opacity = '0';
    secondsectionwrapper.style.display = 'block';
    secondsection.style.position = 'fixed';
    secondsection.style.left = '50%';
    secondsection.style.top = '50%';
    secondsection.style.transform = 'translateX(-50%)';
  }
};

onMounted(() => {
  addEventListener("scroll", (event) => {});
});
</script>

<template>
  <div class="bg-[#111111] w-full h-full absolute outside">
    <section class="h-full">
      <nav class="text-white flex items-center justify-end mt-5 pr-6">
        <!-- <img src="../assets/me.jpeg" class="absolute shadow-black shadow-md -left-1 top-10 w-[60px] m-4 rounded-full" alt=""> -->
        <a class="font-bold uppercase absolute left-6 md:left-8 md:mt-0 mt-6" href="">JacksWeb</a>
        
        <ul class="hidden md:flex">
          <li class="duration-200 hover:bg-red-900 px-3 py-1 rounded-full cursor-pointer">Home</li>
          <li class="duration-200 hover:bg-red-900 px-3 py-1 rounded-full cursor-pointer">Services</li>
          <li class="duration-200 hover:bg-red-900 px-3 py-1 rounded-full cursor-pointer">Portfolio</li>
          <li class="duration-200 hover:bg-red-900 px-3 py-1 rounded-full cursor-pointer">About</li>
          <li class="duration-200 hover:bg-red-900 px-3 py-1 rounded-full cursor-pointer">Contact</li>
        </ul>
        
        <input id="toggle" type="checkbox" class="hidden">
        
        <label @click="expandnav" for="toggle" class="hamburger absolute top-4 right-6 cursor-pointer md:hidden">
          <div class="top-bun"></div>
          <div class="meat"></div>
          <div class="bottom-bun"></div>
        </label>
      </nav>
      
      <header class="inline-flex font-[roboto] items-center text-white">
        <section class="w-[325px] absolute md:top-40 top-28 left-6 md:left-14 duration-500 z-50 backdrop-blur-lg p-4 rounded-md title">
          <h1 class="md:text-3xl text-xl font-bold uppercase">Hand-coded Websites</h1>
          
          <p class="mt-2 opacity-70 duration-200 md:text-base text-sm">Why settle for an average website when you have an exceptional idea? <br>
            Get a hand-coded website today!
          </p>
          <hr class="mt-4 border-2 rounded-full">
        </section>
      </header>
      
      <section class="h-[40%] mt-[370px] md:p-10 p-2 text-white md:max-w-3xl mx-auto duration-1000 swipercontainer">
        <swiper class="size-full" 
        :slides-per-view="1.5" 
        :space-between="30"
        :pagination="{ clickable: true }" 
        :navigation="{ nextEl: '.swiper-button-next', prevEl: '.swiper-button-prev' }"
        :initial-slide="1"
        :centered-slides="true">
        <swiper-slide class="slides slide1">
          <h2 class="font-bold uppercase">Hand-coded over Drag and drop</h2>
          <p class="opacity-80">Hand-coded websites offer precise customisation, superior performance, scalability, efficient code, and greater control over security.</p>
        </swiper-slide>
        
        <swiper-slide class="slides slide2">
          <h2 class="font-bold uppercase">5 years of coding experience</h2>
          <p class="opacity-80">With 5 years of coding experience, I can create a website that is tailored to your needs. Using best practices, I can quickly and efficiently code your website.</p>
        </swiper-slide>
        
        <swiper-slide class="slides slide3">
          <h2 class="font-bold uppercase">Extensive Experience and education</h2>
          <p class="opacity-80">With a bachelors in cybersecurity and an internship under my belt, your website will be secure and as fast as ever.</p>
        </swiper-slide>
        
        <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div>
      </swiper>
    </section>
  </section>
  
  <section class="h-[200%] flex items-end secondsectionwrapper">
    <section class="w-full h-full duration-500 opacity-0 md:p-10 p-3 fixed left-1/2 top-1/2 -translate-x-1/2 secondsection">
      <div class="w-full text-white md:gap-10 gap-2 grid place-items-center grid-cols-1 md:grid-cols-2 max-w-4xl">
        <div class="bg-[#ffffff30] backdrop-blur-md md:p-8 p-4 rounded-lg duration-700 max-w-md -translate-x-56 opacity-0" id="top-left-slide">
          <h2 class="font-bold mb-4 uppercase">title one here</h2>
          <p class="md:text-base text-sm">description goes here. place holder at the moment just so i can see what thius would look like,will cange in  a bit</p>
        </div>
        <div class="bg-[#ffffff30] backdrop-blur-md md:p-8 p-4 rounded-lg duration-700 max-w-md translate-x-56 opacity-0" id="top-right-slide">
          <h2 class="font-bold mb-4 uppercase">title one here</h2>
          <p class="md:text-base text-sm">description goes here. place holder at the moment just so i can see what thius would look like,will cange in  a bit</p>
        </div>
        <div class="bg-[#ffffff30] backdrop-blur-md md:p-8 p-4 rounded-lg duration-700 max-w-md -translate-x-56 opacity-0" id="bottom-left-slide">
          <h2 class="font-bold mb-4 uppercase">title one here</h2>
          <p class="md:text-base text-sm">description goes here. place holder at the moment just so i can see what thius would look like,will cange in  a bit</p>
        </div>
        <div class="bg-[#ffffff30] backdrop-blur-md md:p-8 p-4 rounded-lg duration-700 max-w-md translate-x-56 opacity-0" id="bottom-right-slide">
          <h2 class="font-bold mb-4 uppercase">title one here</h2>
          <p class="md:text-base text-sm">description goes here. place holder at the moment just so i can see what thius would look like,will cange in  a bit</p>
        </div>
      </div>
    </section>
  </section>
  
  <section class="h-full bg-blue-500 duration-200 flex items-end justify-center thirdsection">
    <swiper class="w-full h-1/2 max-w-3xl mb-20 opacity-0 duration-500 secondswiper"
    :slides-per-view="1"
    :space-between="30"
    :pagination="{ clickable: true }" 
    :navigation="{ nextEl: '.swiper-button-next', prevEl: '.swiper-button-prev' }"
    :centered-slides="true">
    
    <swiper-slide class="bg-white/25 rounded-md" id="portfolio-1"></swiper-slide>
    <swiper-slide class="bg-white/25 rounded-md"></swiper-slide>
    <swiper-slide class="bg-white/25 rounded-md"></swiper-slide>
    <swiper-slide class="bg-white/25 rounded-md"></swiper-slide>
    <swiper-slide class="bg-white/25 rounded-md"></swiper-slide>
    
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
  </swiper>
</section>
</div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@500&display=swap');
.secondsection, .thirdsection {
  background-color: #111111;
}
.outside {
  background-image: url('../assets/rect.png');
  background-size: 70% 30%;
  background-repeat: no-repeat;
  background-position: top right;
}

@media screen and (max-width: 768px) {
  .outside {
    background-size: 70% 15%;
  } 
}

.me {
  background-image: url('../assets/me.png');
  background-size: cover;
}

.slides:nth-child(1) {
  background-image: url('https://images.unsplash.com/photo-1446034295857-c39f8844fad4?q=80&w=1770&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
}
.slides:nth-child(2) {
  background-image: url('https://images.unsplash.com/photo-1707345512638-997d31a10eaa?q=80&w=1770&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
}
.slides:nth-child(3) {
  background-image: url('https://images.unsplash.com/photo-1461301214746-1e109215d6d3?q=80&w=1770&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
}

.slides {
  @apply bg-cover md:h-auto h-[80%] md:p-4 p-3 gap-4 rounded-lg bg-[#ffffff] flex items-center justify-center flex-col text-center duration-200;
  background-blend-mode: multiply;
  background-color: #00000090;
  transition: opacity 0.2s ease;
}

.slides:not(.swiper-slide-active) {
  @apply opacity-20;
}

:global(.swiper-pagination-bullet) {
  background: white;
}

.swiper-button-prev, .swiper-button-next {
  @apply text-white;
}
.swiper-button-prev::after, .swiper-button-next::after {
  @apply text-3xl;
}

.hamburger div {
  position: relative;
  width: 1.7em;
  height: 3.5px;
  border-radius: 3px;
  background-color: white;
  margin-top: 5px;
  transition: all 0.3s ease-in-out;
}
#toggle:checked + .hamburger .top-bun {
  transform: rotate(-45deg);
  margin-top: 14px;
}
#toggle:checked + .hamburger .bottom-bun {
  opacity: 0;
  transform: rotate(45deg);
}
#toggle:checked + .hamburger .meat {
  transform: rotate(45deg);
  margin-top: -2.5px;
}
#toggle:checked + .hamburger + .nav {
  top: 0;
  transform: scale(1);
}

#portfolio-1 {
  background-image: url('../assets/ahdrumservices.png');
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
