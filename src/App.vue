<template lang="pug">
  #app
    .row
      .col-sm-12 
        h1 Calculadora
    .row
      .col-3
        //TODO: Mostrar texto de input centrado
        b-input.tamano(type="text" size="lg" v-model="contenidoEnTextArea" readonly id="inputDeNumeros")
        b-button.cuadro(@click="deleteAll") C
        b-button.cuadro +/-
        b-button.cuadro %
        b-button.cuadro DEL
        b-button.cuadro(v-for="number in numbers" @click="writeNumber(number)" v-bind:value="number") {{number}}
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      numbers: [0,1,2,,3,4,5,"x",6,7,8,"-",9,".","=","+"],
      contenidoEnTextArea: ""
    }
  },
  methods:{
    deleteAll(){
      this.contenidoEnTextArea = ""
    },
    writeNumber(number){
      this.contenidoEnTextArea += number
      if(number === "+"){
        
      }
    }
  }
}
</script>

<style lang="stylus">
.cuadro
  display inline-block
  width 60px
  height 50px
  margin 5px
  padding 10px 
  text-align center
.tamano
  width 270px
  margin-left 5px
</style>
