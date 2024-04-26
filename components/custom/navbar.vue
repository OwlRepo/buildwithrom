<template>
    <div class="flex justify-between py-5">
        <Drawer>
            <DrawerTrigger class="sm:hidden">
                <Button variant="outline">
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
                        <Button variant="outline">Home</Button>
                        <Button variant="outline">Projects</Button>
                        <Button variant="outline">Shorts</Button>
                        <Button variant="outline">About</Button>
                    </div>
                </div>
            </DrawerContent>
        </Drawer>
        <div class="hidden sm:block" />
        <div class="hidden sm:flex items-center rounded-full border border-gray-400 overflow-clip">
            <Button variant="ghost">Home</Button>
            <Button variant="ghost">Projects</Button>
            <Button variant="ghost">Shorts</Button>
            <Button variant="ghost">About</Button>
        </div>
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

</script>