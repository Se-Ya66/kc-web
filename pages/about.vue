<template>
    <div>
        <div class="head-space">
            <v-container>
                <h2 class="heading next">
                    <span
                    v-for="(t, index) in text"
                    :key="index"
                    class="item"
                    :style="{animationDelay: index*100+'ms'}"
                    v-text="t"
                    v-show="visible"
                    />
                </h2>
                <transition name="sub-title">
                    <span class="translate t-next" v-show="visible">私たちについて</span>
                </transition>
            </v-container>
        </div>
        <div class="aboutp-space">
            <div class="top-space">
                <v-container>
                <div class="top-contents">
                    <v-container>
                        <v-row>
                            <transition name="vision">
                                <v-col cols="12" sm="12" md="6" lg="6" v-show="visible">
                                    <h1 class="heading">Vision</h1>
                                    <h2 class="title">社会に必要とされる企業</h2>
                                    <p class="explan">
                                        福岡市内および近郊エリアの収益物件や事業用・
                                        居住用不動産に関する情報と深い知見をもち、
                                        不動産業のプロフェッショナルとして、弊社社名（ミライアークエステート）のとおり、
                                        お客様と不動産の未来へ貢献する架け橋となることを目指します！
                                    </p>
                                </v-col>
                            </transition>
                            <transition name="photo1">
                                <v-col cols="12" sm="12" md="6" lg="6" v-show="visible">
                                    <img src="../static/buil.jpg" class="contents-photo">
                                </v-col>
                            </transition>
                        </v-row>
                    </v-container>
                </div>
                </v-container>
            </div>
            <div class="mid-space">
                <v-container>
                    <div class="mid-contents">
                        <v-container>
                            <v-row>
                                <transition name="vision">
                                    <v-col cols="12" sm="12" md="6" lg="6" v-show="visible2">
                                        <h1 class="heading">Mission</h1>
                                        <h2 class="title">社会に必要とされる企業</h2>
                                        <p class="explan2">
                                            福岡市内および近郊エリアの収益物件や事業用・
                                            居住用不動産に関する情報と深い知見をもち、
                                            不動産業のプロフェッショナルとして、弊社社名（ミライアークエステート）のとおり、
                                            お客様と不動産の未来へ貢献する架け橋となることを目指します！
                                        </p>
                                    </v-col>
                                </transition>
                                <transition name="photo1">
                                    <v-col cols="12" sm="12" md="6" lg="6" v-show="visible2">
                                        <img src="../static/buil.jpg" class="contents-photo">
                                    </v-col>
                                </transition>
                            </v-row>
                        </v-container>
                    </div>
                </v-container>
            </div>
            <div class="mid-space2">
                <v-container>
                    <div class="mid-contents2">
                        <v-container>
                            <v-row>
                                <transition name="photo1">
                                    <v-col cols="12" sm="12" md="6" lg="6" v-show="visible2">
                                        <img src="../static/buil.jpg" class="contents-photo">
                                    </v-col>
                                </transition>
                                <transition name="vision">
                                    <v-col cols="12" sm="12" md="6" lg="6" v-show="visible2">
                                        <h1 class="heading">Mission</h1>
                                        <h2 class="title">社会に必要とされる企業</h2>
                                        <p class="explan2">
                                            福岡市内および近郊エリアの収益物件や事業用・
                                            居住用不動産に関する情報と深い知見をもち、
                                            不動産業のプロフェッショナルとして、弊社社名（ミライアークエステート）のとおり、
                                            お客様と不動産の未来へ貢献する架け橋となることを目指します！
                                        </p>
                                    </v-col>
                                </transition>
                            </v-row>
                        </v-container>
                    </div>
                </v-container>
            </div>
        </div>
        <div class="bottom-space">
            <div class="message">
                <h2 class="heading message-title">Message</h2>
                <v-container>
                <v-row>
                    <v-col cols="12" sm="12" md="6" lg="6">
                        <img src="../static/man2.jpg" class="president">
                    </v-col>
                    <v-col cols="12" sm="12" md="6" lg="6">
                        <p class="message-txt">
                            我々は今まで培った経験と知識とアイデアをもって、世の中に貢献したいという思いからこの会社を設立いたしました。
                        </p>
                        <p class="message-txt">
                            我々は今まで培った経験と知識とアイデアをもって、世の中に貢献したいという思いからこの会社を設立いたしました。
                        </p>
                        <p class="message-txt">
                            我々は今まで培った経験と知識とアイデアをもって、世の中に貢献したいという思いからこの会社を設立いたしました。
                        </p>
                        <p class="message-txt">
                            我々は今まで培った経験と知識とアイデアをもって、世の中に貢献したいという思いからこの会社を設立いたしました。
                        </p>
                        <p class="message-txt">
                            我々は今まで培った経験と知識とアイデアをもって、世の中に貢献したいという思いからこの会社を設立いたしました。
                        </p>
                        <div class="pre-wrap">
                            <p class="prename1">代表取締役</p>
                            <p class="prename2">加藤 惣逸</p>
                        </div>
                    </v-col>
                </v-row>
            </v-container>
            </div>
        </div>
        <div class="bread-space">
            <v-breadcrumbs
            :items="items"
            ></v-breadcrumbs>
            <v-container>
                <v-row align="center" justify="center" class="icon-wrap">
                    <img src="../static/logo4.png" class="icon">
                </v-row>
            </v-container>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            items: [
                {
                    text: 'HOME',
                    disabled: false,
                    to: '/',
                },
                {
                    text: 'ABOUT',
                    disabled: true,
                    to: '/about',
                }
            ],
            text: 'About us',
            visible:false,
            visible2:false,
            visible3:false,
        }
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
        this.visible = !this.visible;
    },
    methods: { 
        handleScroll() {
            if (!this.visible2) {
                const top = document.querySelector('.bottom-space').getBoundingClientRect().top;
                this.visible2 = top < window.innerHeight + 100;
            }
        },
    }
}
</script>

<style>
.bread-space{
    width:100%;
}
.head-space{
    background-color:white;
    color:black;
    line-height: 1;
    padding-top:30px;
}
.next{
    font-weight:400;
}
.t-next{
    opacity:1;
    font-size: 16px;
    color:#a09999;
}
.explan,
.explan2{
    line-height:2;
}
.aboutp-space{
    width:100%;
}
.top-space{
    transform:skew(0deg, -12deg);
    background:#3b5e92; 
    color:#fff;
    height:600px;
    position:relative;
}
.top-contents{
    transform:skew(0deg, 12deg);
    position: absolute;
}

.mid-space{
    padding:40px 0;
}
.mid-space2{
    padding:40px 0;
}
.contents-photo{
    width:100%;
}
.bottom-space{
    background:#3b5e92; 
    width:100%;
    padding:40px 0;
}
.message{
    background:#ffffff; 
    width:90%;
    margin: 0 auto;
    padding: 20px;
}
.message-title{
    text-align: center;
    font-weight: 400;
}
.president{
    width:100%;
}
.message-txt{
    line-height: 2;
}
.pre-wrap{
    margin-top: 50px;
    text-align: right;
    line-height: 0.5;
}
.prename1{
    font-size:15px;
    margin-bottom: -10px;
}
.prename2{
    font-size:20px;
}

@keyframes text-in {
    0% {
        transform: translate(0, -20px);
        opacity: 0;
    }
}
.item {
    display: inline-block;
    min-width: 0.3em;
    font-size: 3rem;
    animation: text-in .8s cubic-bezier(0.22, 0.15, 0.25, 1.43) 0s backwards;
}
.sub-title-enter-active,
.photo1-enter-active {
    transition: opacity 2s;
}
.sub-title-enter, 
.photo1-enter{
    opacity: 0;
}
.sub-title-enter-to,
.photo1-enter-to {
    opacity: 1;
}

.vision-enter-active {
    transition: all 2.0s ease 0s;
}
.vision-enter {
    opacity: 0;
    transform: translateY(-60px);
}
.vision-enter-to {
    transform: translateY(0);
}

@media (min-width:1024px) {
    .aboutp-space{
        height:1100px;
    }
    .top-space{
        padding-top:80px;
        transform:skew(0deg, -15deg);
    }
    .top-contents{
        transform:skew(0deg, 15deg);
    }
    .mid-space{
        display: none;
    }
    .mid-space2{
        padding-top:80px;
        position:relative;
    }
    .mid-contents2{
        padding-top:80px;
        position: absolute;
        top:-100px;
    }
    .mid-head{
        margin-top:-4px;
    }
}


@media (min-width:768px) and ( max-width:1023px) {
    .aboutp-space{
        height:1900px;
    }
    .top-space{
        padding-top:50px;
        transform:skew(0deg, -15deg);
        height:900px;
    }
    .top-contents{
        transform:skew(0deg, 15deg);
    }
    .mid-space{
        position:relative;
    }
    .mid-contents{
        padding-top:80px;
        position: absolute;
        top:0;
    }
    .mid-space2{
        display: none;
    }
    
}

@media (max-width: 767px){
    .mid-space2{
        display: none;
    }
}
</style>