<template>
    <div>
        <v-app-bar 
            flat 
            app 
            color="transparent"
            class="menu">
            <v-spacer />
            <img src="../static/ham2.png" @click="open" v-show="!dialog" class="menu-img">
            <img src="../static/close.png" @click="close" v-show="dialog" class="menu-img">
        </v-app-bar>
        <transition name="modal">
        <div class="bg" v-show="dialog">
            <div class="modal">
                <v-container>
                    <transition name="modal-contents">
                        <v-row class="contents" v-show="dialog" align-content="center" justify="center">
                            <div class="menu-title">
                                <v-col v-for="(menu, key) in menus" :key="key" 
                                cols="2" sm="2" md="2" lg="2">
                                    <nuxt-link :to="menu.link" class="link">
                                        <div class="links">
                                            <p class="menu-name" @click="close">{{menu.name}}</p>
                                        </div>
                                    </nuxt-link>
                                </v-col>
                            </div>
                        </v-row>
                    </transition>
                </v-container>
                <transition name="logo">
                    <img src="../static/logo.png" class="logo" v-show="dialog">
                </transition>
            </div>
        </div>
        </transition>
    </div>
</template>

<script>


export default {
    data(){
        return{
            dialog: false,
            menus:[
            {   
                name:'Home',
                link:'/' ,
                sub:'ホーム'
            },
            {   
                name:'About',
                link:'/about' ,
                sub:'私たち'
            },
            {   
                name:'Bussiness',
                link:'/business' ,
                sub:'事業'
            },
            {   
                name:'News',
                link:'/news' ,
                sub:'ニュース'
            },
            {   
                name:'Company',
                link:'/company' ,
                sub:'企業'
            },
            {   
                name:'Contact',
                link:'/' ,
                sub:'企業'
            },
        ],
        }
    },
    methods:{
        open(){
            this.dialog = true;
        },
        close(){
            this.dialog = false;
        },
    },
    
}
</script>

<style>
.v-app-bar-nav-icon{
    margin-right: 30px;
}
.menu{
    z-index:5;
}
.menu-img{
    width:110px;
    cursor: pointer;
}

.bg{
    background-color: rgba(59, 94, 146, 0.9);
    color:white;
    width:100%;
    height:100vh;
    position: fixed;
    display: flex;
    left: 0;
    top: 0;
    z-index:4;
    font-family: 'Noto Sans JP', sans-serif;
    letter-spacing: 3px;
    padding-top:75px;
    padding-left:90px;
}
.contents{
    
    z-index:3;
    position: absolute;
    top: 0;
    bottom: 0;
    margin: auto;
}

.menu-name {
    color:white;
    position: relative;
    display: inline-block;
    transition: 0.5s;
    font-size:30px;
}
.menu-name::after {
    position: absolute;
    bottom: 0;
    left: 0;
    content: '';
    width: 0;
    border-bottom: solid 1px white;
    transition: 0.2s;
}
.menu-name:hover::after {
    width: 100%;
}
.logo{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    width:20%;
    opacity:0.6;
    z-index:2;
}


.modal-leave-active,
.modal-enter-active {
    transition: opacity 0.5s;
}
.modal-enter {
    opacity: 0;
}
.modal-enter-to {
    opacity: 1;
}
.modal-leave {
    opacity: 1;
}
.modal-leave-to {
    opacity: 0;
}

.modal-contents-leave-active, 
.modal-contents-enter-active {
    transform: translate(0px, 0px);
    transition: transform 0.7s cubic-bezier(0, 0, 0.2, 1) 0ms;
}
.modal-contents-enter, .modal-contents-leave-to {
    transform: translateY(10vh) translateY(0px);
} 

.logo-leave-active,
.logo-enter-active {
    transform: scale(0, 0);
    transition: transform 0.7s;
}
.logo-enter-to, .logo-leave {
    transform: scale(1, 1);
}

@media (min-height:768px) and ( max-height:1023px) {
    .logo{
        width:30%;
    }
    .menu-name {
        font-size:5vw;
    }
    .contents{
        position: absolute;
        top: 0;
        bottom: 0;
        margin: auto;
    }
}
@media (min-height: 661px) {
    .logo{
        width:35%;
    }
    .menu-name {
        font-size:5vw;
    }
}

@media (min-height: 611px) and ( max-height:660px){
    .logo{
        width:25%;
    }
    .menu-name {
        font-size:2.5vw;
        
    }
}
@media (min-height:550px) and ( max-height:610px) {
    .logo{
        width:30%;
    }
    .menu-name {
        font-size:5vw;
    }
    .contents{
        left:0;
        right:0;
        position: absolute;
        top: 0;
        bottom: 0;
        margin: auto;
    }
}
@media (max-height: 549px){
    .logo{
        width:30%;
    }
    .menu-name {
        font-size:3vw;
        line-height:2px;
    }
    
}

</style>