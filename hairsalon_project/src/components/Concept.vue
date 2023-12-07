<script setup>

    import { ref } from 'vue'
    
    const concept = ref('CONCEPT')
    const concept_title = ref('自分らしさを引き立てる、心地よい美の場所')
    const concept_text = ref('私たちの美容院は、お客様一人ひとりの個性と美しさを大切にし、心地よいひとときを提供することをコンセプトにしています。\n私たちはトレンドに捉われない永続的で自然な美しさを追求し、お客様が日々の喧騒から離れリラックスできる特別な空間を提供します。')

</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <div class="concept_container">

            <h1>{{ concept }}</h1>
            <p class="title">{{ concept_title }}</p>
            <p class="text">{{ concept_text }}</p>

        </div>

    </body>

</template>

<style scoped>

    .concept_container{
        width: 100%;
        text-align: center;
    }

    /* mobile */
    @media(max-width: 480px){
        
        h1{
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

        .title{
            margin-top: 25px;
            font-size: x-small;
            font-family: sans-serif;
            font-weight: bolder;
        }

        .text{
            margin-top: 15px;
            font-size: 7px;
            white-space: pre-line;
            line-height: 11px;
            font-family: sans-serif;
        }

    }

    /* pc */
    @media(min-width: 481px){

        h1{
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

        .title{
            margin-top: 60px;
            font-size: large;
            font-family: sans-serif;
            font-weight: bold;
        }
        
        .text{
            margin-top: 40px;
            white-space: pre-line;
            line-height: 25px;
            font-family: sans-serif;
        }
        
    }
    
</style>