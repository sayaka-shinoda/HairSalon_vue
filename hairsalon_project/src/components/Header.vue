<script setup>
    import { ref } from 'vue'
</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <img src="../assets/hairsalon_logo.png" alt="logo" class="logo_img" />

    </body>

</template>

<style scoped>
    /* mobile */
    @media(max-width: 480px){
        
    .logo_img{
        display: block;
        width: 45px;
        height: 45px; 
        margin: auto;
    }
    }
    /* pc */
    @media(min-width: 481px){
        
    .logo_img{
        display: block;
        width: 120px;
        height: 120px; 
        margin: auto;
    }
    }
</style>