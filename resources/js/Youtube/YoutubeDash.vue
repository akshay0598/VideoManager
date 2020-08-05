<template>
<div class = "YoutubeDash__wrapper">
<video-group :videos = "videos"></video-group>
</div>
</template>

<script>
import Search from './Search';
import VideoGroup from './VideoGroup.vue';
export default{
components:{
VideoGroup
},
created(){
Search({
apiKey:'AIzaSyAqEpwVsdiU7njsexjQ-aRM7nds-jz6oQ0',
term:'laravel repository',

},response => this.videos = response);
},
data(){
return{

videos:null
}
}

}

</script>
