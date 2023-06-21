<template>
    <nav class="border-secondary-lighter bg-secondary-lighter py-0 bg-[#24272C]">
        <div class="main-navbar z-[100]">
            <div class="flex h-full w-fit items-center md:pr-6">
                <div class="pl-4 md:pr-8">
                    <a href="/" class="block w-20"><KickLogo /></a>
                </div>
                <div class="hidden h-full md:block">
                    <div class="nav-group flex items-center h-full">
                        <a href="#" class="h-full text-base font-bold leading-[60px] text-white transition-all duration-75 ease-in hover:text-[#53FC18]">Browse</a>
                        <a href="#" class="h-full text-base font-bold leading-[60px] text-white transition-all duration-75 ease-in hover:text-[#53FC18] ml-[2.25rem]">Following</a>
                        <div class="relative !ml-2 text-left">
                            <div class="flex items-center md:gap-5">
                                <button class="hidden rounded p-2 px-2.5 hover:bg-secondary-lightest md:block text-white">
                                    <div style="width: 20px; height: 20px;"><HeaderDots /></div>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="max-w-[320px] basis-[100%]">
                <form class="search-header">   
                    <div class="relative">
                        <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                            <svg aria-hidden="true" class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path></svg>
                        </div>
                        <input type="search" id="search" class="block w-full p-4 pl-10 text-sm text-white border border-[#191b1f] focus:border-black rounded-lg bg-[#191b1f]" placeholder="Search" required>
                    </div>
                </form>
            </div>
            <div class="flex w-full items-center justify-end px-2 md:w-fit lg:px-3">
                <div>
                    <button type="button" class="flex text-sm bg-gray-800 rounded-full focus:ring-4 focus:ring-gray-300 dark:focus:ring-gray-600" aria-expanded="false" data-dropdown-toggle="dropdown-user">
                        <img class="w-10 h-10 rounded-full" src="https://dbxmjjzl5pc1g.cloudfront.net/296c3690-eee0-4661-b328-46e633323036/images/user-profile-pic.png" alt="user photo">
                    </button>
                </div>
            </div>
        </div>
    </nav>
</template>

<style lang="scss" scoped>

.search-header{
    input{
        padding:8px 12px 8px 34px;
        outline: none;
    }
}
.main-navbar{
    position: sticky;
    display: flex;
    height: 60px;
    width: 100%;
    flex-grow: 1;
    align-content: space-between;
    align-items: center;
    justify-content: space-between;
    text-align: center;
}

</style>