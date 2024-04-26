<template>
    <div>
        <section class="flex flex-col my-24 md:mt-36">
            <h2 class="mt-10 scroll-m-20 pb-2 text-5xl font-semibold tracking-tight transition-colors first:mt-0">
                Hello!
            </h2>
            <h1 class="scroll-m-20 text-5xl font-bold tracking-tight lg:text-7xl">
                You can call me <span
                    class="bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text text-transparent">Romeo</span>
            </h1>
            <p class="leading-7 mt-3 text-xl">
                Front-end Engineer at <a href="#"
                    class="bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text text-transparent">
                    Samsung
                </a>
            </p>
            <p class="leading-7 my-7 md:w-[65%]">
                I'm a UI engineer who crafts pixel-perfect interfaces using cutting-edge frameworks
                with <strong>React and Vue ecosystem.</strong> Let's build something amazing together!
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
        <section class="flex flex-col py-20">
            <div class="flex items-center">
                <div class="flex flex-col mt-5 items-center md:mx-auto overflow-clip">
                    <h2
                        class="scroll-m-20 text-xl font-semibold tracking-wide transition-colors first:mt-0 text-primary">
                        Colleagues
                    </h2>
                    <h2 class="scroll-m-20 text-4xl font-semibold tracking-wide transition-colors first:mt-0">
                        Thoughts about me
                    </h2>
                    <div class="flex p-1 space-x-5 mt-10 ">
                        <Card v-for="(_, index) in 5">
                            <CardContent class="flex space-x-10 p-6 w-[700px]">
                                <div class="flex flex-col justify-center flex-[2] items-center">
                                    <Avatar class="mb-3">
                                        <AvatarImage src="https://github.com/radix-vue.png" alt="@radix-vue" />
                                        <AvatarFallback>CN</AvatarFallback>
                                    </Avatar>
                                    <small>John Doe</small>
                                    <small><b>Front End Engineer</b></small>
                                </div>
                                <div class="flex flex-col justify-center flex-[8]">
                                    <i>
                                        <small>
                                            &ldquo;John is a talented front-end engineer with a keen eye for
                                            detail and a
                                            deep understanding of HTML, CSS, and JavaScript. He consistently
                                            delivers high
                                            quality work and is always eager to learn and improve. He is a
                                            team
                                            player,
                                            communicates effectively, and is always open to feedback and
                                            constructive
                                            criticism. I highly recommend John for any front-end related
                                            hiring
                                            needs.&rdquo;
                                        </small>
                                    </i>
                                </div>
                            </CardContent>
                        </Card>
                    </div>
                </div>
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
