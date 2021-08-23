<template>
  <div id="app">
    <h1>Тестовое задание (микросервис)</h1>
    <hr>
    <Method_A class="methods"
      v-bind:list="list"
      @get-list="getList"
    />
    <Method_B class="methods"
      v-bind:diff="diff"
      @get-diff="getDiff"
    />
  </div>
</template>

<script>
import Method_A from "./components/Method_A";
import Method_B from "./components/Method_B";
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      list: [],
      diff: {},
    }
  },
  components: {
    Method_A,
    Method_B,
  },
  methods: {
    getList() {
      axios.get('http://127.0.0.1:8000/method_a/').then(response => {
        this.list = response.data["Item"];
      })
    },
    getDiff() {
      let code = document.getElementById("inp_code").value
      let date_1 = document.getElementById("inp_date1").value
      let date_2 = document.getElementById("inp_date2").value
      let url = 'http://127.0.0.1:8000/method_b/' + code + '/' + date_1 + '/' + date_2 + '/'
      axios.get('http://127.0.0.1:8000/method_b/' + code + '/' + date_1 + '/' + date_2 + '/').then(response => {
        this.diff = response.data;
      })
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.methods {
  margin-top: 2em;
  margin-left: 2em;
  margin-bottom: 4em;
}
</style>
