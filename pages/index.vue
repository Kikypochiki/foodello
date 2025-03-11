<script setup lang="ts">
const title = ref("Foodello | Home");
const description = ref("A Food Inventory System enabling everyone to be more food thrifty");

useSeoMeta({
 title: () => title.value,
 description: () => `${title.value} - ${description.value}`,
 charset: "utf-8",
 viewport: "width=device-width, initial-scale=1.0",
 robots: "index, follow",

 ogTitle: () => title.value,
 ogDescription: () => `${title.value} - ${description.value}`,

 // ogImage: "https://foodello.vercel.app/featured.jpg",
 // twitterCard: "summary_large_image",
});
</script>

<template>
    <Html lang="en">
    <Head>
    <Link rel="icon" type="image/png" href="/logo.png"></Link>
    <link href="/reset.css" rel="stylesheet" />
    </Head>
    </Html>
   
    <client-only>
    <Welcome />
    </client-only>
   </template>
   
   <style scoped></style>