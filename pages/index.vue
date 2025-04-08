    <script lang="ts"></script>
    <template>
    <client-only>
    <NavBar />
    <div id="fdmain" class="fd-main"></div>
    <Cookies /> 
    <Copyright /> 
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
    const globalDelay = 500;
const allowCookies = useCookie<boolean>("allowCookies", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60 * 24,
});
allowCookies.value = allowCookies.value || false;
async function loadModal() {
 const cookieModal = document.getElementById("fdCookieModal") as HTMLDivElement;
 const cookieBox = document.getElementById("fdCookieBox") as HTMLDivElement;
 const cookieX = document.getElementById("fdCookieX") as HTMLDivElement;
 const cookieOK = document.getElementById("fdCookieOK") as HTMLDivElement;
 if ( !cookieModal || !cookieBox || !cookieX || !cookieOK ) return;
 if (allowCookies.value === true) {
 allowAllCookies();
 return;
 }
 showCookiePopup();
 cookieX.addEventListener("click", (e) => {
 showCookiePopup(false);
 });
 cookieOK.addEventListener("click", (e) => {
 allowAllCookies();
 });
}
async function showCookiePopup(show: boolean = true) {
 const cookieBox = document.getElementById("fdCookieBox") as HTMLDivElement;
 const cookieModal = document.getElementById("fdCookieModal") as HTMLDivElement;
 if (!cookieBox || !cookieModal) {
 setTimeout(showCookiePopup, 50);
 return;
 }
 if (!show) {
 cookieBox.classList.add("fd-hidden");
 cookieModal.classList.add("fd-hidden");
 return;
 }

 cookieBox.classList.remove("fd-hidden");
 cookieModal.classList.remove("fd-hidden");
}
let lastCookieClicked = 0;
async function allowAllCookies() {
 if (lastCookieClicked >= Date.now() - globalDelay) return;
 lastCookieClicked = Date.now();
 allowCookies.value = true;
 showCookiePopup(false);
}
onMounted(() => {
 setTimeout(() => {
 loadModal();
 }, 1);
});
</script>
    <style scoped></style>
    <style></style>