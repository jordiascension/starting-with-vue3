<template>
  <div>
      <!--
          Vamos a capturar el evento que lanza Child
          y llamaremos a un método para que muestre
          los eventargs enviados por el evento.
          1.@my-message es el nombre del evento que quiero
          capturar
          2.captureMyMessage es la función que voy a ejecutar
          cuando reciba el evento, para mostrar los eventargs
      -->
      <Child @my-message="captureMyMessage" />
      Michael Scott once said '{{ mScottDialogue }}'
  </div>
</template>

<script>
import Child from './Child.vue'
export default {
    name: "Parent",
    data() {
        return{
            mScottDialogue: "",
        }
    },
    methods:{
       captureMyMessage (mess) {
           alert(mess)
           console.log(mess)
           this.mScottDialogue = mess
       }
    },
    components:{
        Child,
    }
}
</script>

<style>

</style>