<template>
    <header>
        <img :src="logo" alt="Logo" style="height: 40px;" />
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Projects</a></li>
                <li><a href="#">Services</a></li>
                <li><a href="#">News</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <div class="swiper">
        <div class="swiper-wrapper">
            <div class="swiper-slide" :style="{ backgroundImage: `url(${banner1})` }">
                <div class="slide-overlay"></div>
                <div class="slide-content">
                    <h1>KHANH HOA ADMINISTRATIVE CENTER</h1>
                    <p>Winner at competition 2024</p>
                    <a href="#">Read more</a>
                </div>
            </div>
            <div class="swiper-slide" :style="{ backgroundImage: `url(${banner2})` }">
                <div class="slide-overlay"></div>
                <div class="slide-content">
                    <h1>NEW YORK CONCEPT HOTEL</h1>
                    <p>Hospitality study – 2023</p>
                    <a href="#">Read more</a>
                </div>
            </div>
            <div class="swiper-slide" :style="{ backgroundImage: `url(${banner3})` }">
                <div class="slide-overlay"></div>
                <div class="slide-content">
                    <h1>DA NANG OPERA HOUSE</h1>
                    <p>Cultural project 2022</p>
                    <a href="#">Read more</a>
                </div>
            </div>
        </div>

        <div class="swiper-button-next"></div>
        <div class="swiper-button-prev"></div>
    </div>
</template>

<script>
import { onMounted } from 'vue'
import Swiper from 'swiper/bundle'
import 'swiper/css/bundle'
import logo from '@/assets/images/Logo.png'
import banner1 from '@/assets/images/banner1.jpg'
import banner2 from '@/assets/images/banner2.jpeg'
import banner3 from '@/assets/images/banner3.jpeg'

export default {
    name: 'Header',
    setup() {
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
                    prevEl: '.swiper-button-prev',
                },
            })
        })

        return {
            logo,
            banner1,
            banner2,
            banner3
        }
    }
}

</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body,
html {
    height: 100%;
    font-family: 'Montserrat', sans-serif;
}

header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
    padding: 20px 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: rgba(0, 0, 0, 0.4);
}


nav ul {
    list-style: none;
    display: flex;
    gap: 30px;
}

nav ul li a {
    color: white;
    text-decoration: none;
    text-transform: uppercase;
    font-size: 13px;
    letter-spacing: 1px;
}

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
    font-size: 40px;
    letter-spacing: 6px;
    margin-bottom: 10px;
}

.slide-content p {
    font-size: 14px;
    margin-bottom: 20px;
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

.swiper-button-prev,
.swiper-button-next {
    color: white;
}

header.scrolled {
    background-color: white !important;
    transition: background-color 0.3s, box-shadow 0.3s;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
}

header.scrolled nav ul li a {
    color: black !important;
}
</style>
