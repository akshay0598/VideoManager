<template>
<div class = "VideoGroup__wrapper row grid">
<video-item
v-images-loaded:on.progress="imageProgress"
v-for="video in videos"
:video="video"
:key="video.id.videoId">
</video-item>
</div>
</template>
<script>
import Isotope from 'isotope-layout';
import VideoItem from './VideoItem.vue';
import imagesLoaded from 'vue-images-loaded';
export default{
props:['videos'],
components:{
VideoItem
},
directives:{
imagesLoaded
},
created(){
this.relayoutTheGrid();
},
data(){
return{
isotope:null,
counter:0
}
},
methods:{
relayoutTheGrid(){
var elem = document.querySelector('.grid');
this.isotope = new Isotope(elem,{
itemSelector:'.card',
layoutMode:'masonary'
});
},
imageProgress(instance,img){
console.log('instance',instance,'img',img);
this.counter++;
if(this.counter==20){
}
}
}
}

</script>

<style lang = "scss">
.card{
margin: 0px 5px 5px 0px;
.card-img-top{
max-height:210px;
}
}
</style>
