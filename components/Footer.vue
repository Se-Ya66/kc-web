<template>
    <div class="footer">
        <div class="space1"></div>
        <div class="space2">
            <v-container>
                <v-row 
                    align="center" 
                    justify="center"
                    >
                    <v-col 
                        cols="6" sm="4" md="2" lg="2"
                        v-for="(menu, key) in menus" :key="key"
                        >
                        <nuxt-link :to="menu.link" class="link">
                            <div class="link-box">
                                <span class="link-text">{{menu.name}}</span><br>
                                <span class="link-text sub">{{menu.sub}}</span>
                            </div>
                        </nuxt-link>
                    </v-col>
                </v-row>
            </v-container>
        </div>
        <div class="space3">
            <v-container class="text-center">
                <v-row class="icons" justify="center" align="center">
                    <v-col cols="12" sm="4" md="4" lg="3">
                        <img src="../static/logo2.png" class="footer-img">
                    </v-col>
                    <v-col cols="3" sm="1" md="1" lg="1"
                        v-for="(icon, key) in icons" :key="key">
                        <a href="" class="link-text">
                            <v-icon middle color="white">mdi-{{icon}}</v-icon>
                        </a>
                    </v-col>
                    <v-col cols="12" sm="3" md="3" lg="3">
                        <p class="copyright">© 2020 K&Company</p>
                    </v-col>
                </v-row>
            </v-container>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            menus:[
            {   
                name:'ABOUT',
                link:'/about' ,
                sub:'私たちについて'
            },
            {   
                name:'BUSINESS',
                link:'/business' ,
                sub:'事業紹介'
            },
            {   
                name:'NEWS',
                link:'/news' ,
                sub:'ニュース'
            },
            {   
                name:'PRIVACY POLICY',
                link:'/' ,
                sub:'プライバシーポリシー'
            },
            {   
                name:'COMPANY',
                link:'/company' ,
                sub:'企業情報'
            },
            {   
                name:'CONTACT',
                link:'/' ,
                sub:'お問い合わせ'
            },
        ],
        icons:[
            'twitter',
            'facebook',
            'instagram'
        ]
        }
    }
}
</script>

<style>

.footer{
    background-color: white;
    position:relative;
    width:100%;
    color:white;
}
.space1{
    height:150px;
}
.space2{
    background-color: #34aed7;
    width:90%;
    position: absolute;
    left: 0;
    right: 0;
    margin: auto;
    top:80px;
    padding:80px 0;
    color:white;
}
.space3{
    background-color: #3b5e92;
    padding-top:180px;
}
.dummy{
    text-align: center;
}
.sub-menu{
    font-size: 10px;
    margin-top:5px;
    text-align: center;
}
.sub{
    font-size: 10px;
    text-align: center;
}
.link-box{
    text-align:center;
}
.copyright{
    margin-top: 10px;
    letter-spacing: 1px;
    font-size: 13px;
    color: white;
    opacity: 0.6;
    font-family: 'Roboto', sans-serif;
}
.footer-img{
    width:200px;
}




@media (min-width:768px) and ( max-width:1023px) {
    .space3{
        padding-top:180px;
    }
    .space2{
        padding:50px 0;
    }
    
}
@media (max-width: 767px) {
    .space3{
        padding-top:230px;
    }
    .space2{
        padding:50px 0;
    }
}

</style>
