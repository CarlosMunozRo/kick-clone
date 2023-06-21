<template>
  
  <div>
    <Header></Header>
    <SideBar></SideBar>
    <div class="sm:ml-64">
      <div class=" mt-14">
        <video ref="videoPlayer" class="video-js"></video>
      </div>
    </div>
  </div>

</template>

<script setup>
  import videojs from "video.js";
  import 'video.js/dist/video-js.css'
  import { ref, onMounted } from 'vue'
  const videoPlayer = ref()
  let player = null;
  onMounted(() =>{
    player = videojs(videoPlayer.value, {
      autoplay: false,
      controls: true,
      sources: [
        {
          src: 'http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ElephantsDream.mp4',
          type: 'video/mp4'
        }
      ]
    }, function onPlayerReady() {
      console.log('Player is ready!');
    });
  })
</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap');

*{
  font-family: 'Inter', sans-serif;
}

body{
  background-color: #0B0E0F;
}

.video-js{
  width: 100%;
  min-height: 80vh;
}

.vjs-big-play-button{
  width: 80px;
  height: 80px;
  translate: -50% -50%;

  .vjs-icon-placeholder{
    height: 20px;
    width: 40px;
    position: absolute;
    top: 50%;
    height: 50%;
    translate: -50% -50%;

    &:before{
      translate: 0px -50%;
    }
  }
}

</style>