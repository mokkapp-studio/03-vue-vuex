<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1
      :style="colorContador"
    >
      Contador: {{ contador }}
    </h1>
    <button @click="accionIncrementar">incrementar</button>
    <BtnDisminuir/>
    <hr>
    <BotonAccion :estado="true" />
    <BotonAccion :estado="false" />
    <p>Acceso a contador con mapState a través de las propiedades computadas.</p>
    <p>Las mutaciones solo hacen que modificar el state.</p>
    <p>Las acciones, accionan las mutaciones</p>
  </div>
</template>

<script>
import BtnDisminuir from '../components/BtnDisminuir.vue';
import BotonAccion from '../components/BotonAccion.vue';
import {mapMutations, mapState, mapActions} from 'vuex';
export default {
  name: 'Home',
  components: {
      BtnDisminuir,
      BotonAccion
  },
  computed:{
    ...mapState(['contador']),
    colorContador(){
      return [this.contador > 100 ? {'color': 'green'} : {'color': 'red'}]
    }
  },
  methods: {
    ...mapMutations(['incrementar']),
    ...mapActions(['accionIncrementar'])
  }
}

</script>
