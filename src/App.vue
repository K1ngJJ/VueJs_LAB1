<template>

<router-view></router-view>

</template>

<script>

import Cookies from "js-cookie";

export default {

name: "App",
data() {

return {

deferredPrompt: null

};

},

created() {

window.addEventListener("beforeinstallprompt", e => {

e.preventDefault();

// Stash the event so it can be triggered later.

this.deferredPrompt = e;

if (Cookies.get("add-to-home-screen") === undefined) {

this.deferredPrompt = e;

}

});

window.addEventListener("appinstalled", () => {

this.deferredPrompt = null;

});

},

methods: {

async dismiss() {

Cookies.set("add-to-home-screen", null, { expires: 15 });

this.deferredPrompt = null;

this.deferredPrompt = null;

},

async install() {

this.deferredPrompt.prompt();

}

}

};

</script>