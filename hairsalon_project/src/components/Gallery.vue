<script setup>

    import { ref } from 'vue'

    const gallery = ref('GALLERY')

    /* slide img */
    import gallery_img1 from '@/assets/gallery_img1.jpg';
    import gallery_img2 from '@/assets/gallery_img2.jpg';
    import gallery_img3 from '@/assets/gallery_img3.jpg';
    import gallery_img4 from '@/assets/gallery_img4.jpg';
    import gallery_img5 from '@/assets/gallery_img5.jpg';
  
    const images = ref([
        { src: gallery_img1 },
        { src: gallery_img2 },
        { src: gallery_img3 },
        { src: gallery_img4 },
        { src: gallery_img5 },
    ]);

</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <div class="gallery_container">

            <h1>{{ gallery }}</h1>

        </div>

        <!-- slide img -->
        <div class="slide_container">

            <div class="slides">

                <div v-for="(image, index) in images" :key="index" class="slide">

                <img :src="image.src" alt="slide img" />

                </div>

            </div>

        </div>

    </body>

</template>
  
<style scoped>

    .gallery_container{
        width: 100%;
        text-align: center;
    }

    .slide_container {
        position: relative;
        max-width: 80%;
        overflow: hidden;
    }
  
    .slides {
        display: flex;
        animation: moveSlides 20s infinite linear;
        width: 80%; /* img size */
    }
  
    .slide {
        flex: 0 0 calc(50% - 15px);
    }
  
    .slide img {
        width: 100%;
        height: auto;
    }
  
    @keyframes moveSlides {
        0% { transform: translateX(0); }
        100% { transform: translateX(-100%); }
    }

    /* mobile */
    @media(max-width: 480px) {
        
        h1 {
            display: inline-block;
            position: relative;
            text-align: center;
            margin-top: 25px;
            font-size: small;
            color: #333;
            text-shadow: 0 0 2px white;
        }

        h1::before {
            content: "";
            position: absolute;
            background: #DBB0B0;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            z-index: -1;
        }

        .slide_container {
            margin: 25px auto;
        }

        .slides {
            gap: 10px;
        }

    }

    /* pc */
    @media(min-width: 481px) {

        h1 {
            display: inline-block;
            position: relative;
            margin-top: 80px;
            color: #333;
            text-shadow: 0 0 2px white;
        }

        h1::before {
            content: "";
            position: absolute;
            background: #DBB0B0;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            z-index: -1;
        }
    
        .slide_container {
            margin: 60px auto;
        }

        .slides {
            gap: 15px;
        }

    }

</style>