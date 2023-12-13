<script setup>

    import { ref } from 'vue'

    const reserve = ref('RESERVE')

</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <div class="reserve_container">

            <h1>{{ reserve }}</h1>

        </div>

    </body>

</template>

<style scoped>

    .reserve_container{
        width: 100%;
        text-align: center;
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