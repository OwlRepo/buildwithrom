<template>
    <div class="flex justify-between mt-5">
        <div class="hidden md:flex items-center rounded-full border  border-b-gray-400 border-r-gray-400 overflow-clip">
            <Button variant="ghost" v-for="route in routes" :key="route.name" @click.prevent="goToRoute(route)">
                {{ route.name }}
            </Button>
        </div>
        <Drawer>
            <DrawerTrigger class="md:hidden">
                <Button variant="ghost">
                    <Icon icon="radix-icons:hamburger-menu"
                        class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all" />
                </Button>
            </DrawerTrigger>
            <DrawerContent>
                <div class="mx-auto w-full max-w-sm">
                    <DrawerHeader>
                        <DrawerTitle>Hey, Welcome!</DrawerTitle>
                        <DrawerDescription>Explore my portfolio to know more</DrawerDescription>
                    </DrawerHeader>
                    <div class="grid grid-cols-2 gap-1.5 px-4 pb-4 text-center sm:text-left">
                        <Button variant="ghost" v-for="route in routes" :key="route.name"
                            @click.prevent="goToRoute(route)">
                            {{ route.name }}
                        </Button>
                    </div>
                </div>
            </DrawerContent>
        </Drawer>
        <DropdownMenu>
            <DropdownMenuTrigger as-child>
                <Button variant="outline">
                    <Icon icon="radix-icons:moon"
                        class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
                    <Icon icon="radix-icons:sun"
                        class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
                    <span class="sr-only">Toggle theme</span>
                </Button>
            </DropdownMenuTrigger>
            <DropdownMenuContent align="end">
                <DropdownMenuItem @click="colorMode.preference = 'light'">
                    Light
                </DropdownMenuItem>
                <DropdownMenuItem @click="colorMode.preference = 'dark'">
                    Dark
                </DropdownMenuItem>
                <DropdownMenuItem @click="colorMode.preference = 'system'">
                    System
                </DropdownMenuItem>
            </DropdownMenuContent>
        </DropdownMenu>
    </div>
</template>

<script setup>
import { Icon } from '@iconify/vue'
import { Button } from '@/components/ui/button'
import { DropdownMenu, DropdownMenuContent, DropdownMenuItem, DropdownMenuTrigger } from '@/components/ui/dropdown-menu'
import {
    Drawer,
    DrawerContent,
    DrawerDescription,
    DrawerHeader,
    DrawerTitle,
    DrawerTrigger,
} from '@/components/ui/drawer'

const colorMode = useColorMode()

const routes = [
    {
        name: 'Home',
        path: '/',
    },
    {
        name: 'Projects',
        path: '/projects',
    },
    {
        name: 'Shorts',
        path: '/shorts',
    },
    {
        name: 'About',
        path: '/about',
    },
]

function goToRoute(route) {
    navigateTo(route.path)
}

</script>