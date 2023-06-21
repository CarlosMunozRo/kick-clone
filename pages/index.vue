<template>
  
  <div class="flex h-screen w-full flex-col overflow-hidden">
    <Header></Header>
    <div class="flex grow overflow-hidden">
      <SideBar></SideBar>
      <div class="relative h-full w-full grow overflow-hidden border-l border-[#24272C]">
        <div class="relatize z-10 h-full overflow-y-auto overflow-x-hidden bg-[#0b0e0f]">
          <div class="relative flex h-full w-full">
            <div class="flex h-full w-full grow items-stretch overflow-hidden">
              <div class="scrollbar-none relative flex w-1 grow flex-col overflow-auto overflow-y-auto overflow-x-hidden">
                <video ref="videoPlayer" class="video-js" muted></video>
              </div>
            </div>
            <div class="">
              <div class="chat-container relative h-full" v-bind:class="{'open':toggleChat}">
                <div class="chat-content h-full grow overflow-hidden bg-secondary-dark">
                  <span @click="toggleChat = !toggleChat">CHAT</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default{
  head: {
      title: 'Kick',
  },
  data() {
    return {
      toggleChat: true,
    }
  },
}
</script>

<script setup>
  import videojs from "video.js";
  import 'video.js/dist/video-js.css'
  import { ref, onMounted } from 'vue'


  const videoPlayer = ref()
  let player = null;
  let qualityLevels = null;
  onMounted(() =>{
    player = videojs(videoPlayer.value, {
      autoplay: false,
      controls: true,
      aspectRatio: '16:9',
      sources: [
        {
          src: 'https://vz-b4f1e97e-483.b-cdn.net/65c65840-de66-4c27-afd0-a3b5a904b768/playlist.m3u8',
          type: 'application/x-mpegURL',
          withCredentials: false
        }
      ],
      controlBar: {
          volumePanel: {inline: false},
          pictureInPictureToggle: true,
      },
      enableDocumentPictureInPicture: false,
      disablePictureInPicture:false,
      html5: {
        nativeAudioTracks: true,
        nativeVideoTracks: true,
        nativeTextTracks: true
      }
      }, function onPlayerReady() {
        console.log('Player is ready!');
    });





  })
</script>

<style lang="scss" scoped>

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap');

@font-face {
   font-family: kickplayericons;
   src: url('/fonts/kickplayericons.ttf');
}

*{
  font-family: 'Inter', sans-serif;
}


html {
    line-height: 1.5;
    -webkit-text-size-adjust: 100%;
    -moz-tab-size: 4;
    -o-tab-size: 4;
    tab-size: 4;
    font-family: Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,"Apple Color Emoji","Segoe UI Emoji",Segoe UI Symbol,"Noto Color Emoji";
    font-feature-settings: normal;
    font-variation-settings: normal
}

body{
  background-color: #0B0E0F;
}

/* Hide scrollbar for Chrome, Safari and Opera */
.scrollbar-none::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.scrollbar-none {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}

.chat-container{
  position: relative;
  width: 340px;
  transition: margin-right .15s;
  margin-right: -340px;
  .chat-content{
    opacity: 0;
  }

  &.open{
    margin-right: 0;

    .chat-content{
      opacity: 1;
    }
  }
}


.video-js{
  width: 100%;
}

.vjs-matrix.video-js {
  color: #00ff00;
}
.vjs-matrix .vjs-big-play-button {
  border-color: #00ff00;
}


.video-js .vjs-big-play-button {
  position: absolute;
  top: 50%;
  left: 50%;
  height: 3rem;
  width: 3rem;
  transform: -50% -50%;
  border-radius: 9999px;
  border-width: 0;
  --tw-bg-opacity: 1 !important;
  background-color: rgb(71 79 84 / var(--tw-bg-opacity))!important;
  --tw-shadow: 0 1px 3px 0 rgb(0 0 0 / .1), 0 1px 2px -1px rgb(0 0 0 / .1) !important;
  --tw-shadow-colored: 0 1px 3px 0 var(--tw-shadow-color), 0 1px 2px -1px var(--tw-shadow-color) !important;
  box-shadow: 0 0 #0000,0 0 #0000,var(--tw-shadow)!important;

  .vjs-icon-placeholder:before {
    content: "\f101";
    text-align: center;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}

.video-js .vjs-control-bar{
  background: linear-gradient(180deg,rgba(16,16,16,.02) 0%,rgba(16,16,16,.5) 100%);
}

.video-js .vjs-control{
  width: 4em;
}

.vjs-icon-placeholder:not(.vjs-big-play-button > .vjs-icon-placeholder){
  font-family: kickplayericons!important;
  speak: never!important;
  font-style: normal!important;
  font-weight: 400!important;
  font-variant: normal!important;
  text-transform: none!important;
  line-height: 1!important;
  -webkit-font-smoothing: antialiased!important;
  -moz-osx-font-smoothing: grayscale!important;
}

.vjs-icon-picture-in-picture-enter:before, .video-js .vjs-picture-in-picture-control .vjs-icon-placeholder:before{
  content: "\f121" !important;
}
.vjs-control:hover {
    --tw-text-opacity: 1;
    color: rgb(83 252 24 / var(--tw-text-opacity));
}

.video-js *:not(.vjs-visible-text)>.vjs-control-text{
  border: 0;
    clip: rect(0 0 0 0);
    height: 1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
}

.vjs-control-text {
    font-family: Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,"Apple Color Emoji","Segoe UI Emoji",Segoe UI Symbol,"Noto Color Emoji";
    top: -1.5rem!important;
    left: 50%!important;
    z-index: 50!important;
    display: none!important;
    height: -moz-fit-content!important;
    height: fit-content!important;
    width: -moz-fit-content!important;
    width: fit-content!important;
    --tw-translate-x: -50% !important;
    transform: translate(var(--tw-translate-x),var(--tw-translate-y)) rotate(var(--tw-rotate)) skew(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y))!important;
    white-space: nowrap!important;
    border-radius: 0.125rem!important;
    background-color: #191b1fb3!important;
    padding: 0.375rem!important;
    vertical-align: middle!important;
    font-size: .75rem!important;
    line-height: 1rem!important;
    font-weight: 500!important;
    line-height: 1!important;
    --tw-text-opacity: 1 !important;
    color: rgb(255 255 255 / var(--tw-text-opacity))!important;
    clip: auto!important;
}

.vjs-control:not(.vjs-menu-button):hover .vjs-control-text {
    display: block!important;
}




</style>