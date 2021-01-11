<template>
  <div>
    <Slide />
    <section class="about">
      <div class="txt-space">
        <v-container>
          <v-row align="center" justify="center" style="height: 300px;">
            <transition name="icon">
              <img src="../static/logo4.png" class="icon" v-show="show">
            </transition>
          </v-row>
        </v-container>
      </div>
      <div class="about-space">
        <v-container>
          <div class="txt-wrapper">
            <h2 class="heading news-head">
              <span
              v-for="(t, index) in text"
              :key="index"
              class="item"
              :style="{animationDelay: index*100+'ms'}"
              v-text="t"
              v-show="visible"
              />
            </h2>
            <transition name="about-txt">
              <div v-show="visible2" class="visible2">
                <p class="translate">私たちについて</p>
                <h2 class="title">デジタル領域の制作､広告運用､マーケティング
                全ての機能が連結されたソリューションを提供します</h2>
                <p class="explan">monomodeはデジタル領域を専業とし、
                インターネット広告、デジタルマーケティング等の広告代理店業や
                WEBサイトや映像を中心とした、あらゆるクリエイティブサービス
                自社開発のプロダクトを展開しています。</p>
                  <nuxt-link to="/about" class="link">
                    <div class="button pat1">
                      <span class="one">About Us</span>
                      <span class="sec">></span>
                    </div>
                  </nuxt-link>
              </div>
            </transition>
          </div>
        </v-container>
        <transition name="photo1">
          <img src="../static/buil.jpg" class="photo1" v-show="visible3">
        </transition>
      </div>
    </section>

    <section class="business">
        <v-container>
          <div class="business-wrapper">
            <div class="b-txt-wrapper">
              <h2 class="heading news-head">
                <span
                v-for="(e, index) in text2"
                :key="index"
                class="item"
                :style="{animationDelay: index*100+'ms'}"
                v-text="e"
                v-show="bvisible"
                />
              </h2>
              <transition name="business-txt">
                <div class="b-visible" v-show="bvisible2">
                  <p class="translate">事業紹介</p>
                  <p class="explan">monomodeはデジタル領域を専業とし、
                  インターネット広告、デジタルマーケティング等の広告代理店業や
                  WEBサイトや映像を中心とした、あらゆるクリエイティブサービス
                  自社開発のプロダクトを展開しています。</p>
                </div>
              </transition>
            </div>
            <v-container>
              <v-row justify="center" class="work-card">
                <v-col cols="12" sm="6" md="6" lg="6">
                  <transition name="card1">
                  <div class="work-space" v-show="bvisible3">
                    <v-container>
                      <img src="../static/work.jpg" class="work-img">
                      <div class="card-txt">
                        <p class="work-title">ブライダル・法人営業</p>
                        <div class="line"></div>
                        <p class="work-description">WEBサイトや映像を中心とした、あらゆるクリエイティブサービス自社開発のプロダクトを展開しています。</p>
                        <nuxt-link to="/business" class="link">
                          <div class="links">
                            <p class="work-link">
                              View more
                            </p>
                            <v-icon color="black" small>mdi-chevron-right-circle-outline</v-icon>
                          </div>
                        </nuxt-link>
                      </div>
                    </v-container>
                  </div>
                  </transition>
                </v-col>
                <v-col cols="12" sm="6" md="6" lg="6">
                  <transition name="card2">
                  <div class="work-space" v-show="bvisible4">
                    <v-container>
                      <img src="../static/work.jpg" class="work-img">
                      <div class="card-txt">
                        <p class="work-title">ECサイト</p>
                        <div class="line"></div>
                        <p class="work-description">WEBサイトや映像を中心とした、あらゆるクリエイティブサービス自社開発のプロダクトを展開しています。</p>
                        <div class="links">
                          <a href="https://www.kandc1893.com/"
                          class="work-link">
                            <span class="a-tag">
                            Go to site
                            </span>
                          </a>
                          <v-icon color="black" small>mdi-chevron-right-circle-outline</v-icon>
                        </div>
                      </div>
                    </v-container>
                  </div>
                  </transition>
                </v-col>
              </v-row>
            </v-container>
          </div>
        </v-container>
    </section>

    <section class="news">
      <div class="n-wrapper">
        <v-container>
          <h2 class="heading news-head">
            <span
              v-for="(x, index) in text3"
              :key="index"
              class="item"
              :style="{animationDelay: index*100+'ms'}"
              v-text="x"
              v-show="nvisible"
              />
          </h2>
          <transition name="news-contents">
          <div class="nvisible2" v-show="nvisible2">
          <p class="translate">ニュース</p>
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
          <nuxt-link to="/news" class="link">
                    <div class="button pat2">
                      <span class="one">View More</span>
                      <span class="sec">></span>
                    </div>
                  </nuxt-link>
          </div>
        </transition>
        </v-container>
      </div>
    </section>

    <section class="contact">
      <v-container>
      <h2 class="heading2">Contact</h2>
      <p class="con-txt">
        お問い合わせ
      </p>
      <v-row 
        justify-content="center" 
        class="mt-7">
        <v-col cols="12" sm="6" md="6" lg="6"
        >
        <div class="contact-space form-btn">
          <v-container>
            <h3 class="contact-title">Mail</h3>
            <p>メール</p>
            <p>お問い合わせ・ご相談はお気軽にどうぞ。>
            </p>
          </v-container>
        </div>
        </v-col>
        <v-col cols="12" sm="6" md="6" lg="6"
        >
          <div class="contact-space">
            <v-container>
            <h2 class="contact-title">Tel</h2>
            <p>電話</p>
            <span class="word1">TEL:052-503-5530</span><br>
            <span class="word2">営業時間:9:00~17:00(平日)</span>
            </v-container>
          </div>
        </v-col>
      </v-row>
      </v-container>
    </section>
  </div>
</template>

<script>
import Slide from '~/components/Slide.vue'



export default {
  
  components: {
    Slide,
  },
  data(){
    return{
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
      text: 'About us',
      text2:'Business',
      text3:'News',
      show:false,
      visible:false,
      visible2:false,
      visible3:false,
      bvisible:false,
      bvisible2:false,
      bvisible3:false,
      bvisible4:false,
      nvisible:false,
      nvisible2:false,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
    },
    methods: { 
      handleScroll() {
      if (!this.show) {
        const top = document.querySelector('.about-space').getBoundingClientRect().top;
        this.show = top < window.innerHeight + 100;
      }
      if (!this.visible) {
        const top2 = document.querySelector('.business').getBoundingClientRect().top;
        this.visible = top2 < window.innerHeight + 300;
        this.visible2 = top2 < window.innerHeight + 300;
        this.visible3 = top2 < window.innerHeight + 300;
      }
      if (!this.bvisible) {
        const top3 = document.querySelector('.news').getBoundingClientRect().top;
        this.bvisible = top3 < window.innerHeight + 600;
        this.bvisible2 = top3 < window.innerHeight + 600;
        this.bvisible3 = top3 < window.innerHeight + 700;
        this.bvisible4 = top3 < window.innerHeight + 600;
      }
      if (!this.nvisible) {
        const top4 = document.querySelector('.contact').getBoundingClientRect().top;
        this.nvisible = top4 < window.innerHeight + 200;
        this.nvisible2 = top4 < window.innerHeight + 200;
      }
    },
    }
}
</script>

<style>

/* ボタン */
.button{
  /* text-align: left; */
  color:#3b5e92;
  border:solid 1px #3b5e92;
  position: relative;
  cursor: pointer;
  /* width: 250px; */
  width:35%;
  height: 64px;
  line-height: 64px;
  transition: all 0.3s;
  font-family: 'Source Sans Pro', sans-serif;
  font-weight: 600;
  font-style: italic;
}
.sub-btn{
  margin: 40px 0 40px;
}
.button:hover{
  color:white;
  border:solid 1px #3b5e92;
  background-color: white;
}
.button span{
  z-index:3;
  position: absolute;
}
.one{
  position: absolute;
  top:50%;
	left: 50%;
	transform:translate(-50%, -50%);
}
.sec{
  position: absolute;
  left:80%;
}
.one:hover{
  color:#3b5e92;
}
.sec:hover{
  color:#3b5e92;
}

.button span:hover{
  z-index:3;
  color:#3b5e92;
}
.button::after{
  content: '';
  position: absolute;
  transition: all 0.3s;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: scale(0.1, 0.1);
  z-index:1;
}
.button:hover::after {
  background-color: #3b5e92;
  transform: scale(1, 1);
  z-index:1;
  color:white;
}
/* スペース */


/* アバウト */
.about{
  background-color:#3b5e92;
  color:white;
  padding-bottom:30px;
}
.txt-space{
  background-color:white;
  color:black;
  line-height: 1;
}
.icon{
  width:200px;
}
.about-space{
  background-color:#3b5e92;
  color:white;
  text-align: left;
  position:relative;
  height: 600px;
}
.txt-wrapper{
  width:40%;
}
.explan{
  line-height:2;
}
.photo1{
  position: absolute;
  width:55%;
  top:-15px;
  right:0;
}
.pat1{
  border:solid 1px white;
  color:white;
  margin-top:60px;
}
.pat1:hover{
  color:#3b5e92;
  border:solid 1px white;
  background-color: #3b5e92;
}
.pat1:hover::after {
  background-color: white;
  color:white;
}

/* ビジネス/ */
.business{
  background-color: #d3d3d3;
  text-align: left;
  width:100%;
}
.business-wrapper{
  width:100%;
  height:900px;
}
.work-space{
  background-color:white;
  border-radius: 3px;
  color:black;
  height:560px;
}
.b-txt-wrapper{
  height:200px;
}
.work-img{
  width:100%;
}
.work-title{
  font-size:18px;
}
.card-txt{
  padding:20px 0;
}
.work-description{
  font-family: 'Noto Sans JP', sans-serif;
  font-weight: 300;
}
.line{
  margin-bottom: 10px;
  width:10%;
  border-bottom:1px solid #bbb;
}
.work-link {
  text-align: left;
  color:black;
  position: relative;
  display: inline-block;
  transition: 0.5s;
  font-family: 'Source Sans Pro', sans-serif;
  font-weight: 400;
  font-style: italic;
  letter-spacing: 1px;
  text-decoration: none;
}
.work-link::after {
  position: absolute;
  bottom: 0;
  left: 0;
  content: '';
  width: 0;
  border-bottom: solid 1px black;
  transition: 0.2s;
}
.work-link:hover::after {
  width: 100%;
}

/* ニュース/ */
.news{
  background-color: #3b5e92;
  color:white;
  width:100%;
  padding: 30px;
  height:550px;
}
.n-wrapper{
  height:550px;
}
.news-contents{
  text-align: center;
  margin: 0 auto;
  width:70%;
}
.news-word{
  color: #3b5e92;
  background-color: white;
  margin-left:10px;
  font-size:13px;
}
.news-date{
  color:rgba(255,255,255,0.6);
  font-size:13px;
}
.news-item{
  margin-bottom: 10px;
}
.news-top{
  margin-bottom:10px;
}
.news-bottom{
  border-bottom:1px solid rgba(255,255,255,0.4);
  margin-bottom:20px;
  padding-bottom: 20px;
}
.news-bottom:hover{
  border-bottom:1px solid rgba(255,255,255,1);
}
.news-txt{
  font-size:15px;
}
.pat2{
  border:solid 1px white;
  color:white;
  margin: 0 auto;
  margin-top:60px;
  width:25%;
}
.pat2:hover{
  color:#3b5e92;
  border:solid 1px white;
  background-color: #3b5e92;
}
.pat2:hover::after {
  background-color: white;
  color:white;
}
/* コンタクト */
.contact{
  padding: 30px 0 10px;
}
.con-txt{
  text-align: center;
  margin-top:20px ;
}
.word1{
  letter-spacing: 1px;
  font-size:18px;
}
.word2{
  font-size:13px;
  margin-top:-5px;
  letter-spacing: 1px;
}
.contact-space{
  background-color: #3b5e92;
  border-radius: 3px;
  color:white;
  text-align: center;
  height:200px;
}
.contact-title{
  font-size:40px;
  letter-spacing: 2px;
}
.form-btn{
  cursor: pointer;
  transition: opacity 0.5s
}
.form-btn:hover{
  opacity:0.8;
}

/* トランジション */
.icon-enter-active {
  transition: opacity 3s;
}
.icon-enter {
  opacity: 0;
}
.icon-enter-to {
  opacity: 1;
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

.about-txt-enter-active,
.business-txt-enter-active,
.news-contents-enter-active {
  transition: opacity 4s;
}
.about-txt-enter,
.business-txt-enter,
.news-contents-enter {
  opacity: 0;
}
.about-txt-enter-to,
.business-txt-enter-to,
.news-contents-enter-to {
  opacity: 1;
}
.photo1-enter-active{
  transition: opacity 2s;
}
.photo1-enter {
  opacity: 0;
}
.photo1-enter-to {
  opacity: 1;
}
.card1-leave-active, 
.card1-enter-active {
    transform: translate(0px, 0px);
    transition: transform 0.8s cubic-bezier(0, 0, 0.2, 1) 0ms;
}
.card1-enter, .card1-leave-to {
    transform: translateY(-10vh) translateY(0px);
} 

.card2-leave-active, 
.card2-enter-active {
    transform: translate(0px, 0px);
    transition: transform 0.8s cubic-bezier(0, 0, 0.2, 1) 1ms;
}
.card2-enter, .card2-leave-to {
    transform: translateY(-10vh) translateY(0px);
} 


/* レスポンシブ */
@media (min-width:768px) and ( max-width:1023px) {
  h1,h2,h3,p,span{
    font-size:2vw;
  }
  .about{
    height:1400px;
  }
  .about-space{
    position: relative;
  }
  .txt-wrapper{
    width:90%;
    position: absolute;
    bottom:-400px;
  }
  .photo1{
    width:100%;
    top:0;
    position: absolute;
  }
  .photo1-wrap{
    width:90%;
  }
  .pat1{
    width:30%;
  }
  .business{
    height:800px;
  }
}

@media (max-width: 767px){
  h1,h2,h3,p,span{
    font-size:3vw;
  }
  .button{
    margin: 0 auto;
    height: 50px;
    line-height: 50px;
  }
  .about{
    height:1030px;
  }
  .about-space{
    position: relative;
  }
  .photo1{
    width:100%;
    top:0;
    position: absolute;
  }
  .txt-wrapper{
    width:90%;
    position: absolute;
    bottom:-70px;
  }
  .photo1-wrap{
    width:100%;
  }
  .business{
    height:1150px;
  }
  .pat2{
    font-size:2vw;
    width:40%;
  }
}

</style>