<template>
   <button @click="accionDisminuir(20)">Disminuir</button>
</template>

<script>
import {mapActions} from 'vuex'
export default {
    name: 'BtnDisminuir',
    methods: {
        ...mapActions(['accionDisminuir'])
    }
}
</script>
