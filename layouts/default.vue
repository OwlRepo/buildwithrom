<script setup>
useSeoMeta({
    title: 'Romeo Angeles Jr - Portfolio',
    description: `I'm a UI engineer who crafts pixel-perfect interfaces using cutting-edge frameworks with React and Vue ecosystem. Let's build something amazing together!`,
    ogTitle: 'Romeo Angeles Jr - Portfolio',
})
</script>

<template>
    <div class="container">
        <div class="mx-auto max-w-screen-lg bg-background">
            <CustomNavbar />
            <slot />
        </div>
    </div>
</template>