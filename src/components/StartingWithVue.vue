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
  <div>
      <button type="button" class="btn btn-primary"
       @click="test">Call a method</button>
      <button type="button" class="btn btn-success"
       @click="testWithParameter('Pepe')">Call a method with parameter</button>
  </div>
  <div>
      <ul id="for-example">
          <li v-for="user in users" :key="user.id">
              {{ user.firstName }}
          </li>
      </ul>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
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
       },
       test : function() {
           alert('test function');
       },
       testWithParameter: function(name){
           alert('test function with parameter called ' + name);
       }
   },
   setup(props) {
       alert('The message is ' + props.message);
       const users = ref([
           {firstName: 'Frank', lastName: 'Murphy', age: 24},
           {firstName: 'Vic', lastName: 'Reynolds', age: 30},
           {firstName: 'Gina', lastName: 'Jabowski', age: 40},
           {firstName: 'Jessi', lastName: 'Glaser', age: 50},
           {firstName: 'Jay', lastName: 'Bilzerian', age: 60}
       ]);

       return {
           users
       };

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