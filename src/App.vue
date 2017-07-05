<template>
  <div id="app">
    <!--数据双向绑定-->
    <p>{{message}}</p>
    <input v-model="message"/>
    <!--只赋值一次，不会随message改变而改变-->
    <p v-once>This will never change: {{ message }}</p>
    <!--声明不被vue识别-->
    <p v-html="rawHtml"></p>
    <first-component></first-component>
    <label for="r1">修改颜色</label><input type="checkbox" v-model="class1" id="r1">
    <div v-bind:class="{'class1': class1}">
      directiva v-bind:class
    </div>
    <div v-bind:id="testId"></div>
    {{5+5}}<br>
    {{ ok ? 'YES' : 'NO' }}<br>
    {{ message.split('').reverse().join('') }}
    <div v-bind:id="'list-' + id">My FirstVue</div>
    <p v-if="flag">My FirstVue.js</p>
    {{ message | capitalize }}
    <ol>
      <li v-for="book in books">
        {{ book.text }}
      </li>
    </ol>
    <button v-on:click="reverseMessage">逆转消息</button>
    <table class="">

    </table>
  </div>
</template>

<script>
  import firstComponent from './components/firstComponent.vue'
export default {
  data(){
      return {
        message:"hello World",
        rawHtml:"{{message}}",
        class1: false,
        testId:1,
        ok:false,
        id:2,
        flag:true,
        books: [
          { text: '学习 JavaScript',name:'hhx' },
          { text: '学习 Vue' },
          { text: '整个牛项目' }
        ]
      }
  },
  components:{firstComponent},
  filters: {
    capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1)
    }
  },
  methods: {
    reverseMessage: function () {
        console.log(1);
        console.log($("#app").html())
      this.phone = '123';
      this.message = 'hxh';
    }
  }
}
</script>

<style>
  .class1{
    background: #444;
    color: #eee;
  }
</style>
