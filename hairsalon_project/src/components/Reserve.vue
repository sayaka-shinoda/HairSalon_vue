<script setup>

    import { ref } from 'vue'

    const reserve = ref('RESERVE')

    const reserve_web = ref('WEB予約')
    const reserve_tel = ref('TEL予約')

</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <div class="reserve_container">

            <h1>{{ reserve }}</h1>

        </div>

        <div class="reserve_btn">

        <p class="web_btn">{{ reserve_web }}</p>
        <p class="tel_btn">{{ reserve_tel }}</p>

        </div>

    </body>

</template>

<style scoped>

    .reserve_container{
        width: 100%;
        text-align: center;
    }

    .reserve_btn{
        width: 100%;
        display: flex;
        justify-content: center;
        margin: 50px 0;
    }
    
    .web_btn,
    .tel_btn{
        position:relative;
        /*ボタンの形状*/
        display:inline-block;
        margin: 0 50px;
        padding: 10px 30px; 
        color:#544a47;
        border:1px solid #544a47;
        text-decoration: none;
        outline: none;
        transition:all 0.3s ease-in-out;
        cursor: pointer;
    }

    .web_btn:hover,
    .tel_btn:hover{
        background:#544a47;
        color: #fff;
        border-color:transparent;
    }

    .web_btn::before,
    .web_btn::after,
    .tel_btn::before,
    .tel_btn::after {
        content:''; 
        position:absolute;
        border:solid #544a47;
        width:10px;
        height:10px;
        transition:all 0.3s ease-in-out;
    }

    .web_btn::before,
    .tel_btn::before{
        top:-6px;
        left:-6px;
        border-width:1px 0 0 1px;
    }

    .web_btn::after,
    .tel_btn::after{
        bottom:-6px;
        right:-6px;
        border-width:0 1px 1px 0;
    }

    .web_btn:hover::before,
    .web_btn:hover::after,
    .tel_btn:hover::before,
    .tel_btn:hover::after{
        width:calc(100% + 11px);
        height:calc(100% + 11px);
        border-color:#544a47;
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

        .reserve_btn{
            margin: 30px 0;
        }

        .web_btn,
        .tel_btn{
            margin: 0 25px;
            padding: 5px 15px;
            font-size: x-small;
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

    }

</style>