<template>
  <div id="firstComponent">
    <h1>I am a title.</h1>
    <p> written by {{ author }} </p>
    <p>phone is {{phone}}</p>
    <button v-on:click="update">更新</button>
  </div>
</template>

<script type="text/javascript">
  export default {
    data () {
      return {
        phone:12131231,
        author: "胡XX"
      }
    },
    methods:{
        update:function () {
          this.phone = "123";
        }
    }
  }
</script>

<style>
</style>
