<script setup>
import { ref, onMounted } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/swiper-bundle.css';
import SwiperCore, { Pagination, Navigation } from 'swiper/core';

SwiperCore.use([Pagination, Navigation]);

const showAuth = ref(false);

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

function collapseslides() {
  const slides = document.querySelectorAll('.offercontainers');

  slides.forEach(slide => {
    if (slide.style.marginBottom === '-100px') {
      slide.style.marginBottom = '8px';
    } else {
      slide.style.marginBottom = '-100px';
    }
  });
}
</script>


<template>
  <div class="bg-[#1c1c1c] w-full h-full outside" id="app">
    <section class="portfolio-section size-full flex items-center justify-center flex-col">
      <section class="topbackground w-full flex items-center justify-center flex-col pb-10">
        <nav class="flex items-center fixed h-14 top-4 w-[90%] max-w-3xl justify-end z-40 pr-6 py-4 rounded-2xl text-white bg-white/15 backdrop-blur-md left-1/2 duration-500 -translate-x-1/2">
          
          <a class="font-bold uppercase absolute left-4" href="">JacksWeb</a>
          
          <ul class="hidden gap-4 md:flex text-sm">
            <li class="duration-200 rounded-full cursor-pointer">Home</li>
            <li class="duration-200 rounded-full cursor-pointer">Portfolio</li>
            <li class="duration-200 rounded-full cursor-pointer">Services</li>
            <li class="duration-200 rounded-full cursor-pointer">Contact</li>
          </ul>
          
          <input id="toggle" type="checkbox" class="hidden">
          
          <label @click="expandnav" for="toggle" class="hamburger cursor-pointer md:hidden">
            <div class="top-bun"></div>
            <div class="meat"></div>
            <div class="bottom-bun"></div>
          </label>
        </nav>
        
        <h1 class="text-white text-4xl text-center pb-2 md:mt-32 mt-28 font-semibold px-4">Hand-coded websites</h1>
        <p class="text-sm text-center max-w-2xl pb-2 border-b-[3px] w-3/4 md:w-unset border-white/70 text-white/70 mb-20 px-4">Why settle for an average website when you have an exceptional idea?</p>
        
        <section class="w-[90%] gap-8 text-xl border-2 bg-[#1c1c1c] rounded-md md:p-4 p-3 max-w-3xl flex items-end mx-auto">
          <div class="md:w-[20%] hidden md:block scale-[1.45] mr-10 mb-4 -rotate-6">
            <img class="overflow-hidden shadow-2xl shadow-white/40 border-2 border-white/70 rounded-md" src="../assets/me.png" alt="">
          </div>
          
          <div class="text-white md:w-[80%]">
            <img class="h-[100px] rounded-md border-2 md:hidden absolute right-2 -mt-20 shadow-black" src="../assets/me.png" alt="">
            
            <p class="text-base md:text-xl">Hello👋, my name is <span class="text-orange-600 font-bold">Jack!</span></p>
            <p class="text-base md:text-xl">I am a <span class="text-orange-600 font-bold">web developer</span>, <span class="text-orange-600 font-bold">cyber security</span> professional, and <span class="text-orange-600 font-bold">AI enthusiast!</span></p>
            <ul class="font-light text-xs md:text-base mt-4 opacity-80 ml-4 list-disc">
              <li>5 years experience in web developing & cybersecurity.</li>
              <li>Bachelors of Science in cybersecurity including web developing.</li>
              <li>Web development university teacher.</li>
            </ul>
          </div>
        </section>
      </section>
      
      <section class="md:w-[90%] md:mt-10 mt-10 mx-auto flex flex-col items-center justify-center text-white">
        <h2 class="text-2xl mb-6 border-b-[3px] px-2 inline-flex pb-2 border-white/70">Examples of my work</h2>
        
        <section class="grid grid-cols-2 md:flex gap-3 md:flex-wrap md:items-center md:justify-center w-[90%] max-w-5xl mx-auto">
          <a href="https://ahdrumservices.com" target="_blank">
            <div class="bg-[#1c1c1c] flex flex-col gap-1 pl-4 justify-center md:w-[200px] py-2 md:py-6 hover:bg-[#222222] duration-200">
              <img class="w-8 -ml-1" src="../assets/websiteicon.png" alt="">
              <h2 class="text-lg">Drumming services</h2>
              <p class="opacity-60 text-xs">Simple, single-page website developed efficiently with advanced technologies</p>
            </div>
          </a>
          
          <a href="https://ahdrumservices.com" target="_blank">
            <div class="bg-[#1c1c1c] flex flex-col gap-1 pl-4 justify-center md:w-[200px] py-4 md:py-6 hover:bg-[#222222] duration-200">
              <img class="w-8 -ml-1" src="../assets/websiteicon.png" alt="">
              <h2 class="text-lg">Local football club</h2>
              <p class="opacity-60 text-xs">Advanced, multi-page website with admin & editing functions.</p>
            </div>
          </a>
          
          <a href="https://jackhughes03.github.io/AI-Project/" target="_blank">
            <div class="bg-[#1c1c1c] flex flex-col gap-1 pl-4 justify-center md:w-[200px] py-4 md:py-6 hover:bg-[#222222] duration-200">
              <img class="w-8 -ml-1" src="../assets/websiteicon.png" alt="">
              <h2 class="text-lg">AI website</h2>
              <p class="opacity-60 text-xs">Simple, single page website with an advanced & modern design.</p>
            </div>
          </a>
          
          <a href="https://ahdrumservices.com" target="_blank">
            <div class="bg-[#1c1c1c] flex flex-col gap-1 pl-4 justify-center md:w-[200px] py-4 md:py-6 hover:bg-[#222222] duration-200">
              <img class="w-8 -ml-1" src="../assets/websiteicon.png" alt="">
              <h2 class="text-lg">JacksWeb</h2>
              <p class="opacity-60 text-xs">Advanced, single-page website using latest technologies and designs.</p>
            </div>
          </a>
          
          <a href="https://ahdrumservices.com" target="_blank">
            <div class="bg-[#1c1c1c] flex flex-col gap-1 pl-4 justify-center md:w-[200px] py-4 md:py-6 hover:bg-[#222222] duration-200">
              <img class="w-8 -ml-1" src="../assets/websiteicon.png" alt="">
              <h2 class="text-lg">Website Example 1</h2>
              <p class="opacity-60 text-xs">Description of this website example goes hereeeeee eeeeeeeeee</p>
            </div>
          </a>
          
          <a href="https://ahdrumservices.com" target="_blank">
            <div class="bg-[#1c1c1c] flex flex-col gap-1 pl-4 justify-center md:w-[200px] py-4 md:py-6 hover:bg-[#222222] duration-200">
              <img class="w-8 -ml-1" src="../assets/websiteicon.png" alt="">
              <h2 class="text-lg">Website Example 1</h2>
              <p class="opacity-60 text-xs">Description of this website example goes hereeeeeeeeee eeeeeee</p>
            </div>
          </a>
        </section>
      </section>
      
      <section class="size-full text-white text-center items-center  overflow-x-clip px-1 mt-32 max-w-4xl">
        <h2 class="text-3xl mb-12 border-b-[3px] px-2 border-white/70 inline-flex pb-2">Services I offer</h2>
        <button @click="collapseslides" class="mb-10 p-1 px-4 rounded-md cursor-pointer bg-white text-black">Collapse</button>
        
        <div class="offercontainers ml-auto rotate-3">
          <div class="pl-2">
            <h3>Single-page website</h3>
            <p>This is a discriptive description that needs to be changed. It can be anything but this is a placeholder right now.</p>
          </div>
          
          <img class="offerblocks" src="https://cdn.pixabay.com/photo/2018/05/04/20/01/website-3374825_1280.jpg" alt="">
        </div>
        
        <div class="offercontainers -rotate-3">
          <img class="offerblocks" src="https://cdn.pixabay.com/photo/2016/09/21/11/24/carousel-1684591_1280.png" alt="">
          
          <div>
            <h3>Multi-page website</h3>
            <p>This is a discriptive description that needs to be changed. It can be anything but this is a placeholder right now.</p>
          </div>
        </div>
        
        <div class="offercontainers ml-auto rotate-3">
          <div class="pl-2">
            <h3>Design</h3>
            <p>This is a discriptive description that needs to be changed. It can be anything but this is a placeholder right now.</p>
          </div>
          
          <img class="offerblocks" src="https://cdn.pixabay.com/photo/2018/08/18/13/26/interface-3614766_1280.png" alt="">
        </div>
        
        <div class="offercontainers -rotate-3">
          <img class="offerblocks" src="https://cdn.pixabay.com/photo/2018/04/29/20/45/laptop-3361063_1280.jpg" alt="">
          
          <div>
            <h3>Admin</h3>
            <p>This is a discriptive description that needs to be changed. It can be anything but this is a placeholder right now.</p>
          </div>
        </div>
        
        <div class="offercontainers ml-auto rotate-3">
          <div class="pl-2">
            <h3>Editing</h3>
            <p>This is a discriptive description that needs to be changed. It can be anything but this is a placeholder right now.</p>
          </div>
          
          <img class="offerblocks" src="https://cdn.pixabay.com/photo/2018/05/04/00/09/design-3372889_1280.jpg" alt="">
        </div>
      </section>
      
      <section class="size-full text-white text-center mt-32 max-w-4xl pb-10">
        <h2 class="text-3xl mb-12 border-b-[3px] px-2 border-white/70 inline-flex pb-2">Contact me</h2>
        
        <form class="flex flex-col gap-4 items-center justify-center" action="https://api.staticforms.xyz/submit" method="post">
          <input class=" p-4 bg-[#1c1c1c] border-2 border-white/70 rounded-md" type="text" placeholder="Name" name="name">
          <input class="p-4 bg-[#1c1c1c] border-2 border-white/70 rounded-md" type="text" placeholder="Email" name="email">
          <textarea class="w-[40%] p-4 bg-[#1c1c1c] border-2 border-white/70 rounded-md" placeholder="Message" name="message"></textarea>
          <input type="text" name="honeypot" style="display:none">
          <input type="hidden" name="accessKey" value="e749ad79-4651-42be-bd1c-a06af7678d6c">
          <input type="hidden" name="subject" value="Contact us from - example.com" />
          <input type="hidden" name="replyTo" value="@">
          <input type="hidden" name="redirectTo" value="https://example.com/contact/success">
          <button class="px-4 bg-[#1c1c1c] border-2 border-white/70 rounded-md hover:bg-white hover:text-black duration-200">Send</button>
        </form>
      </section>
    </section>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Signika+Negative:wght@300..700&display=swap');
.topbackground {
  background-image: url('https://cdn.pixabay.com/photo/2020/04/22/12/12/background-5077810_1280.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-color: #11111170;
  background-blend-mode: multiply;
}
.offercontainers {
  @apply flex items-center border-2 shadow-xl shadow-[#111111] justify-center gap-10 text-left bg-[#1c1c1c] p-4 rounded-md max-w-2xl mb-2 duration-500;
  .offerblocks {
    @apply bg-white w-[100px] md:w-[300px] md:h-[150px] rounded;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
  }
  
  h3 {
    @apply md:text-2xl font-semibold;
  }
  p {
    @apply md:text-sm text-xs opacity-80 mt-2;
  }
}

.portfolio-section {
  background-color: #151515;
}

nav {
  box-shadow: 0 10px 30px 0 #111111;
}
.secondsection {
  background: linear-gradient(to top, #000222, #000000);
}
nav, .title, section {
  font-family: 'Signika Negative', sans-serif;
  letter-spacing: 1px;
}
.fourthsection, .thirdsection {
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
  @apply bg-cover md:h-auto h-[100%] p-4 gap-4 rounded-lg bg-[#ffffff] flex items-center justify-center flex-col text-center duration-200;
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
