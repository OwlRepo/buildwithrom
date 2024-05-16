<template>
    <div>
        <div class="flex flex-col md:flex-row items-center space-x-0 md:space-x-16 mt-16">
            <div
                class="h-52 w-3 rounded-full bg-gradient-to-b from-primary to-fuchsia-500 hidden md:block animate-pulse" />
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
                    with <strong
                        class="bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text text-transparent">React
                        and Vue ecosystem.</strong> Let's build something amazing together!
                </p>
                <div class="flex space-x-4">
                    <Button variant="outline">
                        Career Highlights
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
            <a href="https://app.daily.dev/romeoangelesjr">
                <img 
                src="https://api.daily.dev/devcards/v2/iGo5aeTE4EVvxH2gBN2Ae.png?type=default&r=t8q" 
                class="shadow-lg border border-gray-200 rounded-lg dark:border-none"
                alt="Romeo Angeles JR's Dev Card"/>
            </a>
        </div>

        <Icon icon="radix-icons:arrow-down" role="button"
            class="h-[2rem] w-[2rem] p-[5px] rotate-0 scale-100 transition-all cursor-pointer animate-bounce border dark:border-white border-primary rounded-full mx-auto mt-10 mb-40" />

        <div
            class="flex flex-col-reverse md:flex-row items-center w-full md:space-x-10 space-x-0 md:h-[200px] md:p-20 rounded-md md:overflow-y-clip mb-20 md:bg-gradient-to-br md:from-20% md:dark:from-black md:border md:border-gray-300 dark:border-none md:dark:to-fuchsia-500">
            <div class="flex flex-col">
                <p class="bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text text-transparent w-fit text-lg">
                    Multi-Platform</p>
                <b class="text-3xl">Reaching users on every screen</b>
                <p class="leading-7 mt-2">I have developed applications using modern frameworks to enhance
                    development speed and user experience across mobile, web, desktop, and embedded devices.
                </p>
            </div>
            <iframe src="https://lottie.host/embed/1c0295e6-bf3e-4d16-9848-2e1fa6255490/iyTBGMvWLc.json"
                class="md:h-[500px] md:w-[800px] h-[300px] w-[300px]" />
        </div>

        <div class="flex flex-col mt-36">
            <div
                class="h-[10px] w-20 rounded-full bg-gradient-to-b from-primary to-fuchsia-500 block mb-5 md:mx-auto " />
            <h1 class="scroll-m-20 w-fit text-5xl font-bold lg:text-4xl mx-auto">
                Career Highlights
            </h1>

            <div class="grid grid-cols-1 gap-20 md:my-10 my-20 ">
                <div class="flex flex-col space-y-16">
                    <div v-for="experience in workExperience" :key="experience.name" class="flex space-x-2">
                        <small class="text-gray-400 text-xs  w-[200px] h-fit border-l-2 border-l-primary pl-2">{{
                            experience.date
                            }}</small>
                        <div class="flex flex-col">
                            <small class="font-bold">{{ experience.name }}</small>
                            <small>{{ experience.description }}</small>
                            <div class="flex space-x-2 mt-5">
                                <small v-for="tech in experience.tech" :key="tech">
                                    <Badge class="text-white bg-fuchsia-500">{{ tech }}</Badge>
                                </small>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="flex flex-col space-y-5 justify-end items-stretch">
                    <div class="flex space-x-2 items-center">
                        <Icon icon="radix-icons:stack" role="button" class="h-[2rem] w-[2rem]" />
                        <h1 class="scroll-m-20 w-fit text-2xl font-bold lg:text-3xl mx-auto">
                            Projects
                        </h1>
                    </div>
                    <Carousel class="relative w-full ">
                        <CarouselContent>
                            <CarouselItem v-for="(project, index) in projects.reverse()" :key="index">
                                <div class="p-1">
                                    <Card>
                                        <CardContent class="flex aspect-video p-6 relative flex-col md:flex-row md:items-center items-stretch">
                                            <NuxtImg :src="project.banner" class="md:w-1/2 object-contain mb-5 md:mb-0 rounded-md bg-red-400 h-fit"/>
                                            <div class="flex flex-col md:p-5 justify-center">
                                                <Badge v-if="project.protected" class="text-white bg-red-400 w-fit my-3">N.D.A Protected</Badge>
                                                <p class="text-2xl md:text-4xl font-semibold" :class="{
                                                    'hover:bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text hover:text-transparent': !project.protected 
                                                }" :role="project.protected ? 'text' : 'button'" @click.prevent="!project.protected && windowOpen(project.redirectUrl)">
                                                {{project.title}}
                                                </p>
                                                <small>{{ project.desc }}</small>
                                                <hr class="my-5"/>
                                                <small>Role</small>
                                                <strong class="bg-gradient-to-r from-primary to-fuchsia-500 bg-clip-text text-transparent w-fit">{{ project.role }}</strong>
                                                <br/>
                                                <small class="mb-2">Technology Stack</small>
                                                <div class="flex flex-wrap">
                                                    <small v-for="stack in project.stack" :key="stack">
                                                        <Badge class="text-white bg-fuchsia-500 mr-2 mb-2">{{ stack }}</Badge>
                                                    </small>
                                                </div>
                                            </div>
                                        </CardContent>
                                    </Card>
                                </div>
                            </CarouselItem>
                        </CarouselContent>
                        <CarouselPrevious class="hidden lg:flex" />
                        <CarouselNext class="hidden lg:flex" />
                    </Carousel>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { Icon } from '@iconify/vue'

const workExperience = [
    {
        name: 'My Portfolio',
        description: 'This is my portfolio. I developed it using Nuxt 3, Tailwind, and Radix UI. I hope you like it. This is my portfolio. I developed it using Nuxt 3, Tailwind, and Radix UI. I hope you like it.',
        tech: ['Nuxt 3', 'Tailwind', 'Radix UI'],
        date: '2023 - PRESENT',
    },
    {
        name: 'My Portfolio',
        description: 'This is my portfolio. I developed it using Nuxt 3, Tailwind, and Radix UI. I hope you like it. This is my portfolio. I developed it using Nuxt 3, Tailwind, and Radix UI. I hope you like it.',
        tech: ['Nuxt 3', 'Tailwind', 'Radix UI'],
        date: '2023 - PRESENT',
    },
]

const projects = [
    {
        title: 'TALK(QUICKTALK)',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/quicktalk.png?alt=media&token=ef280e11-8ffe-4d92-96a7-513e886e14e0',
        protected: true,
        role: 'Mobile Developer',
        stack:['Android Studio','XCode', 'Flutter','Java','SwiftUI','Dart'],
        desc: "Formerly known as QuickTalk, it is an application that's focused on providing Real Time Communcations to connect brands, people and things anytime and anywhere.",
    },
    {
        title: 'TALK ADMIN',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/no-banner.jpg?alt=media&token=9204eb44-8e68-48e2-9325-cd4f20d77213',
        protected: true,
        role: ['Web Developer', 'Product Designer', 'NextJS Developer'],
        role: 'Lead Web Developer, Product Designer',
        stack:['NextJS','ChakraUI','Javascript'],
        desc: "A web application that's focused on managing the TALK Mobile Application.",
    },
    {
        title: 'FIDOMONEY',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/fidomoney.png?alt=media&token=4d01353b-f2dd-45e5-969e-250865809793',
        protected: true,
        role: 'Lead Mobile Developer, Product Designer',
        stack:['Flutter','Dart','Firestore'],
        desc: 'Fidomoney is one of the only companies in the financial market that exclusively supplies digital payment solutions.',
    },
    {
        title: 'MYNTHCHAIN',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/Screenshot_20230219_041450.png?alt=media&token=f2d1d558-71c7-4ac3-a3e2-42bfcc06aac1',
        protected: true,
        role: 'Lead Web Developer, Product Designer',
        stack:['NextJS','ChakraUI','Javascript'],
        desc: 'The world’s first hybrid digital marketplace for crypto collectables and non - fungible token (NFT)',
    },
    {
        title: 'MYNTHDEX',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/dex.png?alt=media&token=a47c1657-8318-4dfb-b643-7132e7e65551',
        protected: true,
        role: 'Lead Web Developer, Product Designer',
        stack:['NextJS','ChakraUI','Javascript'],
        desc: 'A decentralized crypto exchanges that offer access to digital assets without an intermediary. Instead of relying on a company to fill and record crypto trades, MYNTHDEX offer peer-to-peer (P2P) token swaps using blockchain technology.',
    },
    {
        title: 'MYNTHCHAIN ULTRAVERSE',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/ultraverse.png?alt=media&token=547c3067-ade2-497a-9c0e-9b14cc0f9757',
        protected: true,
        role: 'Lead Web Developer, Product Designer',
        stack:['NextJS','ChakraUI','Javascript'],
        desc: 'A decentralized infrastructure for the AR Ultraverse, merging the physical and virtual world through Augmented Reality, creating a new dimension where everything is possible.',
    },
    {
        title: 'U-PRO PLUS',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/no-banner.jpg?alt=media&token=9204eb44-8e68-48e2-9325-cd4f20d77213',
        protected: true,
        role: 'Lead Mobile Developer, Product Designer',
        stack:['Flutter','Dart'],
        desc: 'A Cross Platform Mobile Application made for advertising purposes such as ADs management for Beauty Salons in Japan',
    },
    {
        title: 'Digipay PH',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/digipay.png?alt=media&token=3ab4e9ee-7b0f-40fd-8e01-c1a813f28ebe',
        protected: true,
        role: 'Lead Web Developer',
        stack:['ReactJS (Class Based Components)','SCSS','Javascript'],
        desc: 'A digital payments and financial services platform with a mobile wallet, an industry leading biller ecosystem, and an interoperable backend.',
    },
    {
        title: 'Digipay PH V2.0',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/digipay.png?alt=media&token=3ab4e9ee-7b0f-40fd-8e01-c1a813f28ebe',
        protected: true,
        role: 'Lead Web Developer',
        stack:['NextJS','Bootstrap','Typescript'],
        desc: 'Revamped and improved version of the Digipay PH that has a digital payments and financial services platform with a mobile wallet',
    },
    {
        title: 'Back Office - Digipay PH',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/backoffice%20digipay.png?alt=media&token=9f3593bd-0ed8-4ff7-a183-de5782cac3c1',
        protected: true,
        role: 'Lead Web Developer, Product Designer',
        stack:['Ruby On Rails','Ruby','SASS','JQuery','Javascript'],
        desc: 'A web application for managing transactions and other related operations.',
    },
    {
        title: 'Back Office - Digipay PH V2.0',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/backoffice%20digipay.png?alt=media&token=9f3593bd-0ed8-4ff7-a183-de5782cac3c1',
        protected: true,
        role: 'Lead Web Developer, Product Designer',
        stack:['NextJS','ChakraUI','Typescript'],
        desc: 'Revamped and improved version of the Digipay PH that focuses on managing transactions and other transaction related stuff that\'s being made on Digipay PH',
    },
    {
        title: 'VIMDESK',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/vimdesk.png?alt=media&token=347c7f68-3d18-4c03-9b44-4ba2436e6865',
        protected: false,
        role: 'Web and Mobile Developer',
        stack:['NuxtJS','VueJS','TailwindCSS','ViteJS','React Native','Javascript'],
        redirectUrl:'https://cotit.io/product',
        desc: 'VimDesk is the operational console that gathers data and follows business activities extensively. With the ability to integrate and /or extract daily software tools such as ERP, MES, CRM, Finance, and more.',
    },
    {
        title: 'COTIT.IO',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/COTIT-IO-SS.png?alt=media&token=3834ad7f-4a5d-4275-82c8-efd33d05e12b',
        protected: false,
        role: 'Lead Web Developer',
        stack:['NuxtJS','VueJS','TailwindCSS','Javascript'],
        redirectUrl:'https://cotit.io/',
        desc: `A solution that offers 360 transparency and control of your business. Their supply chain provides real-time visibility and traceability, ensuring monitoring of goods' movement from origin to destination.`,
    },
    {
        title: 'Denzel Escoto - Portfolio',
        banner:
            'https://firebasestorage.googleapis.com/v0/b/sampleproject-31206.appspot.com/o/Screenshot%202024-05-16%20at%2010.36.57%E2%80%AFPM.png?alt=media&token=d06863e0-4c75-40c4-a4f6-aec5c401acdf',
        protected: false,
        role: 'Lead Web Developer',
        stack:['NuxtJS','VueJS','TailwindCSS','ViteJS','Typescript'],
        redirectUrl:'https://denzelescoto.vercel.app/',
        desc: `A user interface and user experience engineer's web portfolio for Denzel Escoto. A designer who craft a good experience for over 4 years of experience. Specializes in FIGMA.`,
    },
    //TODO: Add more projects
    // 1. COTIT.IO Landing Page
    // 2. VIATAG Admin Dashboard
    // 3. VIMDESK Mobile Application
    // 4. NEONLIFE Landing Page
    // 5. NEONLIFE iOS
    // 6. NEON AI Builder
    // 7. THRIVE Android (In-device AI)
]

function windowOpen(url) {
    window.open(url,'_blank').focus()
}

definePageMeta({
    layout: 'default'
})
</script>
