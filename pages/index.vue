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
                <Video />
                <div class="flex justify-between items-center p-4">
                  <div class="flex items-center gap-x-[20px]">
                    <img class="rounded-full object-cover w-20 h-20" src="https://files.kick.com/images/user/676/profile_image/931b4e8f-5445-427c-bd82-b473530390cc" alt="" />
                    <div class="text-white">
                      <div class="verified flex items-center gap-x-[15px]"><span class="text-[1.25rem] font-bold">xQc</span><span class="text-[#53FC18]"><IconsVerifiedIcon /></span></div>
                      <div class="live-title text-[.875rem] font-medium">My 4th stream.</div>
                      <div class="flex items-center gap-x-[10px]">
                          <a class="text-[.875rem] text-[#53FC18] hover:text-[#3AD305]" href="#">Rocket League</a>
                          <div class="live-tags flex items-center gap-x-[10px]">
                            <span class="tag">English</span>
                            <span class="tag">sports</span>
                            <span class="tag">Action</span>
                          </div>
                      </div>
                    </div>
                  </div>
                  <div>
                    <div class="flex gap-x-[15px]">
                      <a class="btn flex items-center bg-[#53FC18] hover:bg-[#3AD305]" href="#"><IconsFollowIcon /> Follow</a>
                      <a class="btn flex items-center text-white bg-[#3F4448] hover:bg-[#232628]" href="#"><IconsGiftIcon /> Gift a Sub</a>
                      <a class="btn flex items-center text-white bg-[#3F4448] hover:bg-[#232628]" href="#"><IconsSubscribeIcon /> Subscribe</a>
                    </div>
                    <div class="flex gap-x-[15px] justify-end items-center pt-[10px]">
                      <div><IconsViewersIcon /></div>
                      <div class="text-[#53FC18] text-[.875rem] font-bold">10,398 <span class="text-[#929EA6] font-normal">views</span></div>
                      <div><a class="text-white" href="#"><IconsShareIcon /></a></div>
                    </div>
                  </div>
                </div>

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


//MAIN VIEW

.live-tags{
  .tag{
    font-size: .75rem;
    background-color: #202225;
    padding: 0.125rem 0.5rem;
    color: #6B7280;
    border-radius: 999999px;
    transition: all 0.3s ease-in-out;
    cursor: pointer;
    &:hover{
      color: white;
    }
  }
}

.btn{
  display: flex;
  column-gap: 5px;
  height: 2rem;
  padding: 0.375rem 0.5rem;
  font-size: .875rem;
  line-height: 1.25;
  white-space: nowrap;
  width: fit-content;
  flex-wrap: nowrap;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  transition: all .3s ease-in-out;
}

</style>