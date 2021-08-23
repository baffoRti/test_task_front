<template>
  <li>
    <span class="code">{{ item.ISO_Char_Code }}</span> | <span class="name">{{ item.Name }}</span>
  </li>
</template>

<script>
export default {
  name: "List_Item",
  props: {
    item: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style scoped>
li {
  display: flex;
}

.code {
  width: 45px;
  text-align: left;
}

.name {
  width: 400px;
  text-align: left;
  padding-left: 10px;
}
</style>