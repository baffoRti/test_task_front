<template>
  <div>
    <h3 class="text">Метод B</h3>
    <p class="text">Получение разницы курса относительно рубля между двумя датами (Дата 2 > Дата 1). Укажите символьный код валюты и две даты.</p>
    <p class="text">Символьный код:<span><input type="text" class="inp" placeholder="RUS" id="inp_code"></span></p>
    <p class="text">Дата 1:<span><input type="date" class="inp" id="inp_date1"></span></p>
    <p class="text">Дата 2:<span><input type="date" class="inp" id="inp_date2"></span></p>
    <input class="text" type="submit" value="Получить" @click="$emit('get-diff')">
    <p class="text">Курс за дату 1: {{ diff["date_1"] }}</p>
    <p class="text">Курс за дату 2: {{ diff["date_2"] }}</p>
    <p class="text">Разница: {{ diff["diff"] }}</p>
  </div>
</template>

<script>
export default {
  name: "Method_B",
  props: ['diff'],
  components: {
  }
}
</script>

<style scoped>
.text {
  display: flex;
}

span {
  margin-left: 10px;
}

.inp{
  align: right;
}
</style>