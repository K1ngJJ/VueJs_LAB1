<template>
  <admin />
</template>

<script>
import { defineComponent } from 'vue';

import admin from'../components/admin.vue'

export default defineComponent( {
    name: 'adminview',

    components: {
        admin,
    },

});
</script>

<style>

</style>
