    <script lang="ts"></script>
    <template>
    <client-only>
    <NavBar />
    <div id="fdmain" class="fd-main"></div>
    <!-- <Cookies /> -->
    <!-- <Copyright /> -->
    </client-only>
    </template>
    <script setup lang="ts">
    import { useSeoMeta, useHead } from '@vueuse/head';
    const title = "Foodello | Home";
    const description = "A Food Inventory System enabling everyone to be more food thrifty";
    useSeoMeta({
    title: () => title,
    description: () => description,
    charset: "utf-8",
    viewport: "width=device-width, initial-scale=1.0"
    });
    useHead({
    link: [
    {rel: 'icon', type: 'image/png', href: '/logo.png'},
    {rel: 'stylesheet', href: '/reset.css'},
    {rel: 'stylesheet', href: '/custom.css'} ,
    {rel: 'preconnect', href: 'https://fonts.googleapis.com'},
    {rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: ''},
    {rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto+Condensed:ital,wght@0,100..900;1,100..900&family=Underdog&display=swap" rel="stylesheet'}
    ]
    });
    </script>
    <style scoped></style>
    <style></style>