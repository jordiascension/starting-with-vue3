<template>
  <div id="hello-vue">
      {{message}}
  </div>
</template>

<script>
export default {
   name: 'Starting',
   props: {
       message : {required: true, type: String},
       type : {default: 'A', type: String}
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