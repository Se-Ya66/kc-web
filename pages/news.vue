<template>
    <div>
        <div class="head-space2">
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
                    <span class="translate t-next2" v-show="visible">ニュース</span>
                </transition>
            </v-container>
        </div>
        <div class="news-wrap">
            <transition name="news">
                <div v-show="visible">
                    <div v-for="(item, key) in items" :key="key"
                    class="news-contents">
                        <v-row justify-content="left" class="news-top">
                            <span class="news-date">{{item.date}}</span>
                            <span class="news-word">ニュース</span>
                        </v-row>
                        <v-row justify-content="left" class="news-bottom">
                            <nuxt-link to="/" class="link">
                                <span class="link-text news-txt">{{item.title}}</span>
                            </nuxt-link>
                        </v-row>
                    </div>
                </div>
            </transition>
        </div>
        <div class="bread-space">
            <v-breadcrumbs
            :items="contents"
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
            contents: [
                {
                    text: 'HOME',
                    disabled: false,
                    to: '/',
                },
                {
                    text: 'NEWS',
                    disabled: true,
                    to: '/news',
                }
            ],
            items:[
                {
                date:'2020.12.21',
                title:'年末年始の営業について'
                },
                {
                date:'2020.12.20',
                title:'コーポレートサイトをリニューアルしました'
                },
            ],
            text: 'News',
            visible:false,
        }
    },
    mounted() {
        this.visible = !this.visible;
    },
}
</script>

<style>
.news-wrap{
    background-color: #3b5e92;
    color:white;
    width:100%;
    padding: 50px;
    height:80vh;
}

.head-space2{
    background-color: #3b5e92;
    color:white;
    line-height: 1;
    padding-top:30px;
}
.t-next2{
    font-size: 16px;
    color:white;
}
.sub-title-enter-active,
.news-enter-active{
    transition: opacity 2s;
}
.sub-title-enter,
.news-enter {
    opacity: 0;
}
.sub-title-enter-to,
.news-enter-to {
    opacity: 1;
}
</style>