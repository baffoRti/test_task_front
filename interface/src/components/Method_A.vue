<template>
  <div>
    <h3 class="text">Метод A</h3>
    <p class="text">Нажмите на кнопку, чтобы получить список допустимых валют.</p>
    <input class="text" type="submit" value="Получить" @click="$emit('get-list')">
    <List_Item
      v-for="item in list"
      v-bind:item="item"
    />
  </div>
</template>

<script>
import List_Item from "./List_Item";

export default {
  name: "Method_A",
  props: ['list'],
  components: {
    List_Item,
  }
}
</script>

<style scoped>
.text {
  display: flex;
}

input {
  margin-bottom: 1em;
}
</style>