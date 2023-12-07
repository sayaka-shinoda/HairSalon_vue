<script setup>

    import { ref } from 'vue'

    const header_menu = ref('MENU')
    const header_gallery = ref('GALLERY')
    const header_staff = ref('STAFF')
    const header_access = ref('ACCESS')
    const header_recruit = ref('RECRUIT')

    // mobile
    const MobileMenuOpen = ref(false);

    const DrawerMenuBtn = () => {
        MobileMenuOpen.value = !MobileMenuOpen.value;
    };

    const disableScroll = () => {
        document.body.style.overflow = 'hidden';
    };

    const enableScroll = () => {
        document.body.style.overflow = '';
    };
    
</script>

<template>

    <head>

        <meta name="viewport" content="width=device-width" />

    </head>

    <body>

        <div class="header_container">

        <div class="logo_container">
            
            <img src="../assets/hairsalon_logo.png" alt="logo" class="logo_img" />
        
        </div>

        <!-- mobile menu -->

        <nav id="mobile_header">
            
            <button class="mobilemenu_btn" @click="DrawerMenuBtn" :class="{ active: MobileMenuOpen }">
        
                <span></span>
                <span></span>
                <span></span>

            </button>

            <ul v-if="MobileMenuOpen">

                <li>{{ header_menu }}</li>
                <li>{{ header_gallery }}</li>
                <li>{{ header_staff }}</li>
                <li>{{ header_access }}</li>
                <li>{{ header_recruit }}</li>

            </ul>

        </nav>

        <!-- pc menu -->
        <nav id="pc_header">

            <ul>

                <li>{{ header_menu }}</li>
                <li>{{ header_gallery }}</li>
                <li>{{ header_staff }}</li>
                <li>{{ header_access }}</li>
                <li>{{ header_recruit }}</li>

            </ul>

        </nav>

        </div>

    </body>

</template>

<style scoped>

    /* mobile */
    @media(max-width: 480px){

        #pc_header{
            display: none;
        }

        .header_container{
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
        }

        .logo_img{
            width: 45px;
            height: 45px; 
        }

        .logo_container{
            display: flex;
            align-items: center;
            justify-content: center;
            flex: 1;
        }

        #mobile_header{
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        #mobile_header ul{
            display: flex;
            flex-direction: column;
            position: absolute;
            top: 18%;
            left: 50%;
            width: 100%;
            height: 300px;
            padding: 0;
            transform: translate(-50%, -50%);
            align-items: center;
            justify-content: center;
            list-style: none;
            background-color: rgb(140, 140, 140);
            z-index: 80;
        }

        #mobile_header ul li{
            height: 18px;
            margin-top: 15px;
            text-align: center;
            color: #544a47;
            font-size: x-small;
            font-weight: bold;
            transition: .5s;
        }

        #mobile_header ul li:hover{
            color: rgb(180, 180, 180);
        }

        .mobilemenu_btn,
        .mobilemenu_btn span{
            display: inline-block;
            transition: all 0.4s;
            position: relative;
            z-index: 100;
        }

        .mobilemenu_btn{
            position: relative;
            width: 25px;
            height: 25px;
            background: none;
            border: none;
            appearance: none;
            cursor: pointer;
        }

        .mobilemenu_btn span{
            position: absolute;
            left: 5px;
            width: 60%;
            height: 1.5px;
            background-color: #544a47;
            border-radius: 4px;
        }

        .mobilemenu_btn span:nth-of-type(1){
            top: 7px;
        }

        .mobilemenu_btn span:nth-of-type(2){
            top: 12px;
        }

        .mobilemenu_btn span:nth-of-type(3){
            top: 17px;
        }

        .mobilemenu_btn.active span:nth-of-type(1){
            transform: translateY(5px) rotate(-45deg);
            background-color: rgb(180, 180, 180);
        }

        .mobilemenu_btn.active span:nth-of-type(2){
            opacity: 0;
        }

        .mobilemenu_btn.active span:nth-of-type(3){
            transform: translateY(-5px) rotate(45deg);
            background-color: rgb(180, 180, 180);
        }

    }

    /* pc */
    @media(min-width: 481px){
        #mobile_header{
            display: none;
        }
        
        .logo_img{
            display: block;
            width: 120px;
            height: 120px; 
            margin: auto;
        }

        #pc_header ul{
            display: flex;
            justify-content: center;
            list-style: none;
        }

        #pc_header ul li{
            position: relative;
            margin: 30px;
            color: #544a47;
            font-size: large;
        }

        #pc_header ul li::after{
            position: absolute;
            left: 0;
            content: '';
            width: 100%;
            height: 1.5px;
            background-color: #e6b422;
            bottom: -1px;
            transform: scale(0,1);
            transform-origin: center top;
            transition: transform 0.3s;
        }

        #pc_header ul li:hover::after{
            transform: scale(1,1);
        }

    }
    
</style>