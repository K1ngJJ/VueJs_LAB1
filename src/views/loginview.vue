<template>
  <login />
</template>

<script>
import { defineComponent } from 'vue';

import login from'../components/login.vue'

export default defineComponent( {
    name: 'loginview',

    components: {
        login,
    },

});
</script>

<style>

</style>