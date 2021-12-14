<template>
  <div id="hello-vue">
      {{message}}
  </div>
  <div>
      {{count}}
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
  </div>
  <div>
      <img :src="image" v-bind:alt="text" v-bind:[key]="text">
      <img :="imageObject">
  </div>
  <div>
      <p>mensaje original: "{{message}}"</p>
      <p>mensaje invertido computado: "{{reverseMessage}}"</p>
  </div>
  <div v-if="Math.random() > 0.5">
      Ahora me ves
  </div>
  <div v-else>
      Ahora no
  </div>
  <div v-if="type === 'A'">
    A
  </div>
  <div v-else-if="type === 'B'">
    B
  </div>
  <div v-else-if="type === 'C'">
    C
  </div>
</template>

<script>
export default {
   name: 'Starting',
   props: {
       message : {required: true, type: String},
       type : {default: 'A', type: String}
   },
   data: () =>({
       count : 0,
       //mapeo de data properties
       image : "https://lenguajejs.com/javascript/logo.svg",
       text : "Logo de Javascript",
       key: "title",
       //mapeo de objeto
       imageObject: {
           src: "https://lenguajejs.com/javascript/logo.svg",
           alt: "Logo de Javascript",
           title: "Logo de Javascript"
       }
   }),
   computed:{
       reverseMessage : function() {
           return this.message.split('').reverse().join('')
       }
   },
   methods: {
       increment() {
           this.count += 1;
       },
       decrement() {
           this.count -= 1;
       }
   }
}
</script>

<style>
    div{
        font-family: sans-serif;
        border: 1px solid #eee;
        border-radius: 2px;
        padding: 20px 30px;
        margin-top: 1em;
        margin-bottom: 40px;
    }
</style>