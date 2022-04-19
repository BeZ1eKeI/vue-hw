<template>
  <div>
    <div class="display">
      <h1>{{ msg }}</h1>

      <p>Введите число 1</p>
      <input v-model="operand1.number"/>

      <p>Введите число 1</p>
      <input v-model="operand2.number"/>

      <p>Возведение в степень</p>
      <input v-model="operand3"/>

      <p>Результат: = {{result}} </p>
    </div>

    <div class="keyboard">
      <button v-on:click="add">+</button>
      <button v-on:click="sub">-</button>
      <button v-on:click="div">/</button>
      <button v-on:click="mult">*</button>
      <button v-on:click="result = Math.pow(result, operand3)">pow</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalculatorApp',
  props: {
    msg: {
      type: String,
      default: 'Калькулятор'
    },
  },
    data(){
    return {
      text: 'default text from - Calculator.vue',
      operand1: 0,
      operand2: 0,
      operand3: 1,
      result: 0,
    }
  },
  methods: {
    add() {
      this.result = Number(this.operand1) + Number(this.operand2);
    },
    sub() {
      this.result = Number(this.operand1) - Number(this.operand2);
    },
    div() {
      this.result = Math.floor(Number(this.operand1) / Number(this.operand2));
    },
    mult() {
      this.result = Number(this.operand1) * Number(this.operand2);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.display {
  border: 1px solid gray;
}
</style>