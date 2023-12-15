<script setup>

    import { ref } from 'vue'

    const gallery = ref('GALLERY')
    const more = ref('MORE')

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

        <div class="more_btn">

            <p>{{ more }}</p>

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

    .more_btn p{        
        position: relative;
        display: flex;
        justify-content: space-around;
        align-items: center;
        z-index: 0;
        border-top: solid 1px #544a47;
        border-right: solid 1px #544a47;
        border-bottom: solid 1px #544a47;
        border-left: solid 5px #544a47;
        color: #544a47;
        background: #fff;
        transition: 0.3s ease-in-out;
        cursor: pointer;
    }

    .more_btn p:before {
        content: "";
        position: absolute;
        top: 0;
        bottom: 0;
        width: 0;
        display: block;
        background: #544a47;
        transition: .3s;
        left: 0;
    }

    .more_btn p:hover {
        color: #fff
    }

    .more_btn p:hover:before{
        width: 100%;
        z-index: -1;
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
            margin: 0 auto;
            margin-top: 25px;
        }

        .slides {
            gap: 10px;
        }

        .more_btn p{
            margin: 10px 10px 0px auto;
            max-width: 40px;
            padding: 3px 10px;
            font-size: x-small;
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
            margin: 0 auto;
            margin-top: 60px;
        }

        .slides {
            gap: 15px;
        }

        .more_btn p{
            margin: 30px 90px 0px auto;
            max-width: 50px;
            padding: 5px 25px;
        }

    }

</style>