<template>
<div class = "VideoItem__wrapper">
<div class="card" style="width: 18rem;">
<img class="card-img-top" v-bind:src="videoImage" v-bind:alt="videoTitle">
  <div class="card-body">
    <h5 class="card-title">{{videoTitle}}</h5>
    <p class="card-text">{{videoDescription}}</p>
    <a href ="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
</div>
</template>
<script>
export default{
props:['video'],
computed:{
videoTitle(){
return this.video.snippet.title;
},
videoDescription(){
return this.video.snippet.description;
},
videoImage(){
return this.video.snippet.thumbnails.medium.url;

}

}
}

</script>
