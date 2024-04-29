<template>
    <div class="flex items-center space-x-0 md:space-x-16 relative">
        <div class="h-52 w-3 rounded-full bg-gradient-to-b from-primary to-fuchsia-500 hidden md:block animate-pulse" />
        <section class="flex flex-col my-24 md:mt-36">
            <h2 class="mt-10 scroll-m-20 pb-2 text-5xl font-semibold tracking-tight transition-colors first:mt-0">
                Hello!
            </h2>
            <h1 class="scroll-m-20 text-5xl font-bold tracking-tight lg:text-7xl">
                You can call me <span
                    class="bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text text-transparent">Romeo</span>
            </h1>
            <p class="leading-7 my-7 md:w-[65%]">
                I'm a UI engineer who crafts pixel-perfect interfaces using cutting-edge frameworks
                with <strong class="bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text text-transparent">React
                    and Vue ecosystem.</strong> Let's build something amazing together!
            </p>
            <div class="flex space-x-4">
                <Button variant="outline">
                    My Projects
                </Button>
                <Button variant="outline">Learn more about me</Button>
            </div>
            <div class="flex flex-row space-x-4 py-7">
                <TooltipProvider>
                    <Tooltip>
                        <TooltipTrigger as-child>
                            <Icon icon="radix-icons:file-text" role="button"
                                class="h-[1.6rem] w-[1.6rem] rotate-0 scale-100 transition-all cursor-pointer" />
                        </TooltipTrigger>
                        <TooltipContent>
                            <p>Resume</p>
                        </TooltipContent>
                    </Tooltip>
                </TooltipProvider>
                <TooltipProvider>
                    <Tooltip>
                        <TooltipTrigger as-child>
                            <Icon icon="radix-icons:linkedin-logo" role="button"
                                class="h-[1.6rem] w-[1.6rem] rotate-0 scale-100 transition-all cursor-pointer" />
                        </TooltipTrigger>
                        <TooltipContent>
                            <p>LinkedIn</p>
                        </TooltipContent>
                    </Tooltip>
                </TooltipProvider>
                <TooltipProvider>
                    <Tooltip>
                        <TooltipTrigger as-child>
                            <Icon icon="radix-icons:github-logo" role="button"
                                class="h-[1.6rem] w-[1.6rem] rotate-0 scale-100 transition-all cursor-pointer" />
                        </TooltipTrigger>
                        <TooltipContent>
                            <p>Github</p>
                        </TooltipContent>
                    </Tooltip>
                </TooltipProvider>
            </div>
        </section>
    </div>
</template>

<script setup>
import { Icon } from '@iconify/vue'
definePageMeta({
    layout: 'default'
})
</script>
