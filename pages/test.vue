<template>
<div>
    <div class="main_imgBox">
        <img src="https://f.uploader.xzy.pw/eu-prd/upload/20191108160744_61514c415a.jpg" alt="img" class="main_imgM keyframe animation">
        <!-- <img src="https://f.uploader.xzy.pw/eu-prd/upload/20191108160418_5165755153.jpg" alt="img" class="main_imgM"> -->
        
    </div>
</div>
</template>

<script>
export default {
data(){
    return{
    index: 0,
    }
},
mounted() {
    // const images = document.getElementsByClassName('slideshow');
    // this.slideshow(images);
    // setInterval(() => {
    // this.index = this.index < images.length - 1 ? this.index + 1 : 0;
    // this.slideshow(images);
    // }, 7000);
},
methods: {
    // slideshow(images) {
    // const current = images[this.index];
    // const prev = images[this.index - 1] ? images[this.index - 1] : images[images.length - 1];
    // current.classList.add('fadein');
    // current.classList.add('keyframe');
    // current.classList.add('animation');
    // current.classList.remove('fadeout');
    // prev.classList.remove('fadein');
    // prev.classList.add('fadeout');
    // }
}
}
</script>

<style>
.main_imgBox {
    height: 100vh;
    overflow: hidden;
    position: relative; 
}

.main_imgM {
    
    width:100%;
    height:100%;
    object-fit: cover;
    position: absolute;
    left: 0;
    top: 0; 
}
.keyframe {
    animation-name: anim_sc;
}
@keyframes anim_sc {
    0% {
        transform: scale(1.2, 1.2);
    }
    100% {
        transform: scale(1, 1);
        opacity: 0;
    }
}
.animation {
    animation-timing-function: ease-in-out;
    /* animation-iteration-count: infinite; */
    animation-direction: normal;
    animation-duration: 8s;
}


</style>