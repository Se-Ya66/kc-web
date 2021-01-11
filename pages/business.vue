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
        <div class="business-space">
            <v-container v-for="(content, key) in contents" :key="key">
                        <transition name="card">
                <v-row class="business-contents" v-show="visible">
                    <v-container>
                            <v-row justify="space-between" class="spaceb">
                                    <v-col cols="12" sm="12" md="6" lg="6">
                                        <h1 class="title2">{{content.title}}</h1>
                                        <p class="explan">{{content.text}}</p>
                                    </v-col>
                                    <v-col cols="12" sm="12" md="6" lg="5">
                                        <div class="bimg-wrap">
                                            <img :src="content.img" class="business-img">
                                        </div>
                                    </v-col>
                            </v-row>
                    </v-container>
                </v-row>
                        </transition>
            </v-container>
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
                    text: 'BUSINESS',
                    disabled: true,
                    to: '/about',
                }
            ],
            contents:[
                {
                    title: 'ブライダル',
                    text:'monomodeはデジタル領域を専業とし、インターネット広告、デジタルマーケティング等の広告代理店業やWEBサイトや映像を中心とした、あらゆるクリエイティブサービス自社開発のプロダクトを展開しています。',
                    img:require('../static/work.jpg')
                },
                {
                    title: '法人営業',
                    text:'monomodeはデジタル領域を専業とし、インターネット広告、デジタルマーケティング等の広告代理店業やWEBサイトや映像を中心とした、あらゆるクリエイティブサービス自社開発のプロダクトを展開しています。',
                    img:require('../static/work.jpg')
                },
            ],
            text: 'Business',
            visible:false,
        }
    },
    mounted() {
        this.visible = !this.visible;
    },
}
</script>

<style>
.business-space{
    background-color: #d3d3d3;
    width:100%;
    padding:50px;
    margin-top:20px;
}
.title2{
    margin-bottom: 20px;
}
.next{
    font-weight:400;
}
.t-next{
    opacity:1;
    font-size: 16px;
    margin-left:10px;
    color:#a09999;
}
.business-contents{
    background-color: #ffffff;
    height:300px;
    overflow: hidden;
}
.business-contents:first-child{
    margin-bottom:40px;
}
.business-img{
    width:100%;
    margin: 0 auto;
}
.spaceb{
    width:100%;
    height:100%;
    margin: 0 auto;
    overflow: hidden;
}
.bimg-wrap{
    margin:0 auto;
    width:100%;
}

.sub-title-enter-active,
.card-enter-active{
    transition: opacity 2s;
}
.sub-title-enter,
.card-enter {
    opacity: 0;
}
.sub-title-enter-to,
.card-enter-to {
    opacity: 1;
}
</style>