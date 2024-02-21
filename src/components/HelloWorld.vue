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
  secondsectionslides = document.querySelector('.secondsectionslides'),
  headingp = document.querySelector('.title p'),
  secondsection = document.querySelector('.secondsection'),
  thirdsection = document.querySelector('.thirdsection'),
  secondswiper = document.querySelector('.secondswiper'),
  nav = document.querySelector('nav');
  
  if (window.scrollY > 100) {
    swiper.style.transform = 'translateX(1000px)';
    swiper.style.opacity = '0';
  } else {
    swiper.style.transform = 'translateX(0)';
    swiper.style.opacity = '1';
  }
  
  setTimeout(() => {
    if (window.scrollY > 100) {
      headingtitle.innerHTML = 'Services I offer';
      headingp.innerHTML = 'From multi-page websites, to single page, I am trained in all!.';
      
      secondsectionslides.style.opacity = '1';
    } else {
      headingtitle.innerHTML = 'Hand-coded Websites';
      headingp.innerHTML = 'Why settle for an average website when you have an exceptional idea? <br> Get a hand-coded website today!';
      
      secondsectionslides.style.opacity = '0';
    }
  }, 500);
  
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
};

function expandnav() {
  const nav = document.querySelector('nav');
  
  if (nav.style.height === '200px') {
    nav.style.height = '56px';
    nav.style.top = '16px';
    nav.style.width = '90%';
    nav.style.borderRadius = '16px';
  } else {
    nav.style.height = '200px';
    nav.style.top = '0';
    nav.style.width = '100%';
    nav.style.borderRadius = '0';
  }
}

onMounted(() => {
  addEventListener("scroll", (event) => {});
});
</script>

<template>
  <div class="bg-[#000000] w-full h-full absolute overflow-x-clip outside">
    <section class="h-full">
      <div class="w-full max-h-[650px] overflow-hidden absolute opacity-80 mainvideo">
        <video autoplay loop muted src="../assets/nature2.mp4"></video>
      </div>
      
      <nav class="flex items-center fixed h-14 top-4 w-[90%] max-w-3xl justify-end z-40 pr-6 py-4 rounded-2xl text-white bg-white/20 backdrop-blur-md left-1/2 duration-500 -translate-x-1/2">
        <!-- <div class="size-[50px] absolute left-3 top-3 rounded-full border-b-2 meimage"></div> -->
        <a class="font-bold uppercase absolute left-4" href="">JacksWeb</a>
        
        <ul class="hidden gap-4 md:flex text-sm">
          <li class="duration-200 rounded-full cursor-pointer">Home</li>
          <li class="duration-200 rounded-full cursor-pointer">Services</li>
          <li class="duration-200 rounded-full cursor-pointer">Portfolio</li>
          <li class="duration-200 rounded-full cursor-pointer">About</li>
          <li class="duration-200 rounded-full cursor-pointer">Contact</li>
        </ul>
        
        <input id="toggle" type="checkbox" class="hidden">
        
        <label @click="expandnav" for="toggle" class="hamburger cursor-pointer md:hidden">
          <div class="top-bun"></div>
          <div class="meat"></div>
          <div class="bottom-bun"></div>
        </label>
      </nav>
      
      <header class="inline-flex mt-40 font-[roboto] items-center text-white">
        <section class="md:w-[40%] w-[75%] md:max-w-lg fixed md:top-40 top-28 left-2 md:left-14 duration-500 z-30 p-6 rounded-xl title">
          <h1 class="md:text-3xl text-xl font-bold uppercase">Hand-coded Websites</h1>
          
          <p class="mt-2 opacity-70 duration-200 md:text-base text-sm">Why settle for an average website when you have an exceptional idea? <br>
            Get a hand-coded website today!
          </p>
          <hr class="mt-4 border-2 rounded-full">
        </section>
      </header>
      
      <section class="h-[35%] mt-[440px] md:p-6 p-2 text-white md:max-w-3xl mx-auto duration-1000 rounded-2xl swipercontainer">
        <swiper class="size-full rounded-lg"
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
  
  <section class="flex mt-0 items-end secondsectionwrapper">
    <section class="w-full h-full flex flex-col items-center justify-center duration-500 md:p-10 p-3 secondsection">
      <div class="w-full duration-700 pt-20 text-white md:gap-10 gap-2 grid place-items-center grid-cols-1 md:grid-cols-2 max-w-4xl opacity-100 secondsectionslides">
        <div class="bg-[#ffffff30] backdrop-blur-md md:p-8 p-4 rounded-lg duration-700 max-w-md">
          <div class="inline-flex -ml-2 gap-2 items-center justify-center">
            <img class="w-10" src="../assets/singlepage.png" alt="">
            <h2 class="font-bold uppercase">Single page website</h2>
          </div>
          <p class="md:text-base text-sm mt-2">A single-page website consists of only one page with all your content being on it. Depending on what you want, this can be cheaper than a multi-page website.</p>
        </div>
        
        <div class="bg-[#ffffff30] backdrop-blur-md md:p-8 p-4 rounded-lg duration-700 max-w-md">
          <div class="inline-flex -ml-2 gap-2 items-center justify-center">
            <img class="w-10" src="../assets/multipage.png" alt="">
            <h2 class="font-bold uppercase">Multi-page website</h2>
          </div>
          <p class="md:text-base text-sm mt-2">A multi-page website consists of multiple pages to your site. Instead of your content remaining on one, it can be split up. This could be more expensive.</p>
        </div>

        <div class="bg-[#ffffff30] backdrop-blur-md p-4 rounded-lg duration-700 max-w-md text-white">
          <div class="inline-flex -ml-2 gap-2 items-center justify-center">
            <img class="w-10" src="../assets/singlepage.png" alt="">
            <h2 class="font-bold uppercase">Admin login</h2>
          </div>
          <p class="md:text-base text-sm mt-2">A single-page website consists of only one page with all your content being on it. Depending on what you want, this can be cheaper than a multi-page website.</p>
        </div>
        
        <div class="bg-[#ffffff30] backdrop-blur-md p-4 rounded-lg duration-700 max-w-md text-white">
          <div class="inline-flex -ml-2 gap-2 items-center justify-center">
            <img class="w-10" src="../assets/singlepage.png" alt="">
            <h2 class="font-bold uppercase">Admin login</h2>
          </div>
          <p class="md:text-base text-sm mt-2">A single-page website consists of only one page with all your content being on it. Depending on what you want, this can be cheaper than a multi-page website.</p>
        </div>
      </div>
    </section>
  </section>
  
  <section class="h-full bg-blue-500 p-4 duration-200 flex items-end justify-center thirdsection">
    <swiper class="w-full h-1/2 max-w-3xl mb-20 duration-500 secondswiper"
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
@import url('https://fonts.googleapis.com/css2?family=Protest+Riot&display=swap');

nav {
  box-shadow: 0 10px 30px 0 #111111;
}
.secondsection {
  background: linear-gradient(to top, #000222, #000000);
}
nav, .title {
  font-family: 'Protest Riot', cursive;
  letter-spacing: 1px;
}
.thirdsection {
  background-color: #000222;
}
.mainvideo {
  mask-image: linear-gradient(to bottom, white, transparent);
}
.meimage {
  background-image: url('../assets/me.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
/* .outside {
  background-image: url('../assets/rect.png');
  background-size: 70% 30%;
  background-repeat: no-repeat;
  background-position: top right;
  background-attachment: fixed;
} */

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
  @apply opacity-70;
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
  height: 3px;
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
