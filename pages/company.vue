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
                    <span class="translate t-next2" v-show="visible">企業情報</span>
                </transition>
            </v-container>
        </div>
        <div class="company">
            <transition name="company">
                <div class="company-inner" v-show="visible">
                    <v-container>
                        <div v-for="(item, key) in items" :key="key">
                            <v-row 
                            class="profile" justify="start">
                                <v-col md="4">
                                    <p class="profile-title">
                                        {{item.title}}
                                    </p>
                                </v-col>
                                <v-col md="6">
                                    <p class="profile-text">
                                        {{item.text}}
                                    </p>
                                </v-col>
                                <div class="border"></div>
                            </v-row>
                        </div>
                        <v-row>
                            <v-col md="4">
                                <p class="profile-title">
                                    事業内容
                                </p>
                            </v-col>
                            <v-col md="6">
                                <p class="profile-text">
                                    1.ブライダルギフト商品 企画開発 販売事業<br>
                                    2.法人ギフト・ノベルティ商品企画提案<br>
                                    3.EC事業<br>
                                </p>
                            </v-col>
                            <div class="border"></div>
                        </v-row>
                    </v-container>
                </div>
            </transition>
        </div>
        <div class="access">
            <h2 class="access-title">Access</h2>
            <p class="access-subtitle">アクセス</p>
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3259.116957174993!2d136.86193631455325!3d35.22845846227857!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x600374ffd88a8a7f%3A0x221c05dbd1d48c69!2z44CSNDUyLTA4NDEg5oSb55-l55yM5ZCN5Y-k5bGL5biC6KW_5Yy65Z-O6KW_55S677yV77yX!5e0!3m2!1sja!2sjp!4v1609843369007!5m2!1sja!2sjp" width="80%" height="600" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
        </div>
        <div class="bread-space">
            <v-breadcrumbs
            :items="breads"
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
            text: 'Company',
            visible:false,
            items:[
                {
                    title:'社名',
                    text:'株式会社ケイアンドカンパニー',
                },
                {
                    title:'代表取締役',
                    text:'加藤　惣逸',
                },
                {
                    title:'設立',
                    text:'会社',
                },
                {
                    title:'資本金',
                    text:'1000万円',
                },
                {
                    title:'住所',
                    text:'〒452-0841　愛知県名古屋市西区城西町57',
                },
                {
                    title:'TEL / FAX',
                    text:'052-503-5530/052-503-5751',
                },
            ],
            breads: [
                {
                    text: 'HOME',
                    disabled: false,
                    to: '/',
                },
                {
                    text: 'COMPANY',
                    disabled: true,
                    to: '/company',
                }
            ],
        }
    },
    mounted() {
        this.visible = !this.visible;
    },
}
</script>

<style>
.company{
    background-color: #3b5e92;
    width:100%;
    margin: 0 auto;
    padding:100px 0;
}
.company-inner{
    border-top:1px solid #fff;
    width:70%;
    margin: 0 auto;
}
.profile-title{
    color: white;
}
.profile-text{
    color: white;
}
.border{
    width:100%;
    border-bottom:1px solid #fff;
    margin-bottom:10px;
}
.access{
    text-align: center;
    background-color: #3b5e92;
    width: 100%;
    padding-bottom: 50px;
    color:white;
    font-family: 'Noto Sans JP', sans-serif;
}
.access-title{
    margin-bottom:15px;
    letter-spacing: 2px;
    font-size: 3rem;
    font-weight:300;
}
.access-subtitle{
    margin-bottom:30px;
}

.company-enter-active{
    transition: opacity 2s;
}
.company-enter{
    opacity: 0;
}
.company-enter-to{
    opacity: 1;
}
</style>