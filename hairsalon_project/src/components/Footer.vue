<script setup>

    import { ref } from 'vue'

    const footer_text = ref('Copyright © 2023')

</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <div class="footer_container">

            <p>{{ footer_text }}</p>

        </div>

    </body>
    
</template>

<style scoped>

    .footer_container{
        width: 100%;
        padding: 3px 0;
        text-align: center;
        color: white;
        background-color: #544a47;
        font-size: small;
    }

    /* mobile */
    @media(max-width: 480px){

        .footer_container{
            padding: 1px 0;
            font-size: x-small;
        }

    }

</style>