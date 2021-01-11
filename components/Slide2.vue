<template>
    <div>
        <div class="slide-wrapper">
            <img src="../static/09_carousel_01.jpg" class="slideshow">
            <img src="../static/09_carousel_02.jpg" class="slideshow fadeout">
            <img src="../static/09_carousel_03.jpg" class="slideshow fadeout">
        </div>
    </div>
</template>


<script>
export default {
    data: function() {
        return {
        index: 0,
        }
    },
    mounted() {
        const images = document.getElementsByClassName('slideshow');
        this.slideshow(images);
        setInterval(() => {
        this.index = this.index < images.length - 1 ? this.index + 1 : 0;
        this.slideshow(images);
        }, 8000);
        
    },
    methods: {
        slideshow(images) {
        const current = images[this.index];
        const prev = images[this.index - 1] ? images[this.index - 1] : images[images.length - 1];
        prev.classList.remove('fadein');
        prev.classList.add('fadeout');
        current.classList.add('fadein');
        current.classList.add('animation');
        current.classList.add('keyframe');
        current.classList.remove('fadeout');
        }
    }
}
</script>


<style>

.fadein {
opacity: 1;
transition: opacity 3s;
transform: scale(1.2, 1.2);

}
.fadeout {
opacity: 0;
transition: opacity 3s;

}
.slideshow {
position: absolute;
width: 100%;
height:100vh;
}

.slide-wrapper{
    width: 100%;
    height:100vh;
    overflow:hidden;
    position:relative;
}
.keyframe {
animation-name: anim_sc;
}
@keyframes anim_sc {

100% {
    transform: scale(1, 1);
}
}
.animation {
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
    animation-direction: normal;
    animation-duration: 8s;
}

</style>