<script setup>

    import {ref} from 'vue'

    const access = ref('ACCESS')

    const access_place = ref('住所')
    const access_time = ref('営業時間')
    const access_phone = ref('電話番号')
    const access_adress = ref('メールアドレス')

    const place_text = ref('〒123-XXXX\n東京都港区北青山XX-XX')
    const time_text = ref('10:00　～　20:00')
    const phone_text = ref('03-XXXX-XXXX')
    const adress_text = ref('hair-salon.DM@XXXX.jp')

</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <div class="access_container">

            <h1>{{ access }}</h1>

        </div>

        <div class="access_column">

            <div class="access_map">

                <iframe class="mobile_map" src="https://www.google.com/maps/embed?pb=!1m23!1m12!1m3!1d2292.0601155540235!2d139.7106333784811!3d35.665612256854594!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!4m8!3e0!4m0!4m5!1s0x60188c9fee70f285%3A0x4054b8b23563631c!2z6KGo5Y-C6YGT6aeF44CB44CSMTA3LTAwNjEg5p2x5Lqs6YO95riv5Yy65YyX6Z2S5bGx77yT5LiB55uu77yW4oiS77yR77yS!3m2!1d35.6652511!2d139.7120921!5e0!3m2!1sja!2sjp!4v1702371348274!5m2!1sja!2sjp" width="200" height="200" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>

                <iframe class="pc_map" src="https://www.google.com/maps/embed?pb=!1m23!1m12!1m3!1d4584.159636080953!2d139.70935505929535!3d35.66492597801513!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!4m8!3e3!4m0!4m5!1s0x60188c9fee70f285%3A0x4054b8b23563631c!2z6KGo5Y-C6YGT6aeF44CB44CSMTA3LTAwNjEg5p2x5Lqs6YO95riv5Yy65YyX6Z2S5bGx77yT5LiB55uu77yW4oiS77yR77yS!3m2!1d35.6652511!2d139.7120921!5e0!3m2!1sja!2sjp!4v1702275665377!5m2!1sja!2sjp" width="400" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>

            </div>

            <div class="all_container">

                <div class="place_container">

                    <p class="title">{{ access_place }}</p>
                    <p class="text">{{ place_text }}</p>

                </div>

                <div class="time_container">

                    <p class="title">{{ access_time }}</p>
                    <p class="text">{{ time_text }}</p>

                </div>

                <div class="phone_container">

                    <p class="title">{{ access_phone }}</p>
                    <p class="text">{{ phone_text }}</p>

                </div>

                <div class="adress_container">
            
                    <p class="title">{{ access_adress }}</p>
                    <p class="text">{{ adress_text }}</p>

                </div>

            </div>

        </div>

    </body>
    
</template>

<style scoped>

    .access_container{
        width: 100%;
        text-align: center;
    }

    .access_column{
        display: flex;
        width: 100%;
        justify-content: center;
        margin-top: 50px;
    }

    .access_map{
        width: 50%;
        text-align: center;
    }

    .all_container{
        width: 50%;
        line-height: 30px;
    }

    .place_container,
    .time_container,
    .phone_container,
    .adress_container{
        display: flex;
        align-items: center;
    }

    .title{
        width: 35%;
        font-family: sans-serif;
        color: #544a47;
    }

    .text{
        white-space: pre-line;
        font-family: sans-serif;
        color: #544a47;
    }

    /* mobile */
    @media(max-width: 480px){

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

        .access_column{
            margin-top: 30px;
        }

        .pc_map{
            display: none;
        }

        .all_container{
            line-height: 25px;
            font-size: x-small;
        }

        .title{
            width: 40%;
        }

    }

    /* pc */
    @media(min-width: 481px){

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

        .mobile_map{
            display: none;
        }

    }

</style>