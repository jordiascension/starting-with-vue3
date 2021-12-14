<template>
  <div id="hello-vue">
      {{message}}
  </div>
  <div>
      {{count}}
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
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
       count : 0
   }),
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