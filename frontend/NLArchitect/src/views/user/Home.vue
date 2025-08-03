<template>
    <div>
        <div class="swiper">
            <div class="swiper-wrapper">
                <div class="swiper-slide" v-for="(slide, index) in slides" :key="index"
                    :style="{ backgroundImage: `url(${slide.image})` }">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h1>{{ slide.title }}</h1>
                        <p>{{ slide.subtitle }}</p>
                        <a href="#">Read more</a>
                    </div>
                </div>
            </div>
            <div class="swiper-navigation">
                <div class="swiper-button-prev"></div>
                <div class="swiper-button-next"></div>
            </div>

        </div>

        <!-- Giới thiệu -->
        <section class="intro-section">
            <h2>Who we are</h2>
            <p>
                Huni Architectes is an international architecture and urban design office based in Paris and Ho Chi Minh
                City.<br />
                Our work reflects a deep commitment to social, cultural, and environmental context, combining conceptual
                clarity with functional beauty.
            </p>
        </section>
        <section class="intro-section">
            <h2>Who we are</h2>
            <p>
                Huni Architectes is an international architecture and urban design office based in Paris and Ho Chi Minh
                City.<br />
                Our work reflects a deep commitment to social, cultural, and environmental context, combining conceptual
                clarity with functional beauty.
            </p>
        </section>
        <section class="intro-section">
            <h2>Who we are</h2>
            <p>
                Huni Architectes is an international architecture and urban design office based in Paris and Ho Chi Minh
                City.<br />
                Our work reflects a deep commitment to social, cultural, and environmental context, combining conceptual
                clarity with functional beauty.
            </p>
        </section>
        <section class="intro-section">
            <h2>Who we are</h2>
            <p>
                Huni Architectes is an international architecture and urban design office based in Paris and Ho Chi Minh
                City.<br />
                Our work reflects a deep commitment to social, cultural, and environmental context, combining conceptual
                clarity with functional beauty.
            </p>
        </section>
        <section class="intro-section">
            <h2>Who we are</h2>
            <p>
                Huni Architectes is an international architecture and urban design office based in Paris and Ho Chi Minh
                City.<br />
                Our work reflects a deep commitment to social, cultural, and environmental context, combining conceptual
                clarity with functional beauty.
            </p>
        </section>
        <section class="intro-section">
            <h2>Who we are</h2>
            <p>
                Huni Architectes is an international architecture and urban design office based in Paris and Ho Chi Minh
                City.<br />
                Our work reflects a deep commitment to social, cultural, and environmental context, combining conceptual
                clarity with functional beauty.
            </p>
        </section>
    </div>
</template>

<script setup>
import { onMounted } from 'vue'
import Swiper from 'swiper/bundle'
import 'swiper/css/bundle'

const slides = [
    {
        image: new URL('@/assets/images/banner1.jpg', import.meta.url).href,
        title: 'Da Nang Concept House',
        subtitle: 'Winner at competition 2024'
    },
    {
        image: new URL('@/assets/images/banner2.jpeg', import.meta.url).href,
        title: 'Da Nang Concept Hotel',
        subtitle: 'Hospitality study – 2023'
    },
    {
        image: new URL('@/assets/images/banner3.jpeg', import.meta.url).href,
        title: 'Da Nang Opera House',
        subtitle: 'Cultural project 2022'
    }
]

onMounted(() => {
    new Swiper('.swiper', {
        loop: true,
        effect: 'fade',
        autoplay: {
            delay: 5000,
            disableOnInteraction: false,
        },
        navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev'
        }
    })
})
</script>

<style scoped>

.swiper {
    height: 100vh;
}

.swiper-slide {
    position: relative;
    background-size: cover;
    background-position: center;
    
}

.slide-overlay {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.4);
    z-index: 1;
}

.slide-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
    text-align: center;
    z-index: 2;
}

.slide-content h1 {
    font-size: 48px;
    letter-spacing: 10px;
    font-weight: 300;
    text-transform: uppercase;
}

.slide-content p {
    font-size: 16px;
    letter-spacing: 2px;
    margin-bottom: 30px;
}


.slide-content a {
    border: 1px solid white;
    color: white;
    text-decoration: none;
    padding: 10px 20px;
    font-size: 13px;
    transition: 0.3s;
}

.slide-content a:hover {
    background-color: white;
    color: black;
}

.swiper-navigation {
  position: absolute;
  bottom: 20px;
  right: 20px;
  display: flex;
  gap: 10px; 
  z-index: 10;
}

.swiper-button-prev,
.swiper-button-next {
  all: unset; 
  width: 40px;
  height: 40px;
  background-color: rgba(0, 0, 0, 0.5);
  color: rgb(255, 255, 255);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  position: static;
  border: 1px solid rgba(245, 245, 245, 0.5);
}

.swiper-button-prev::after,
.swiper-button-next::after {
  font-size: 16px;
}


/* Intro section */
.intro-section {
    padding: 80px 20px;
    max-width: 1000px;
    margin: auto;
    text-align: center;
}

.intro-section h2 {
    font-size: 28px;
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 20px;
}

.intro-section p {
    font-size: 16px;
    line-height: 1.6;
    color: #444;
}
</style>
