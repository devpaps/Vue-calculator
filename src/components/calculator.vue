<template>
  <div class="calc">
    <h1>{{ title }}</h1>
    <h3>{{ msg }}</h3>

<div class="calculator">
  <div class="display">
    <div class="calculator-formula" v-cloak>{{ tal }}</div>
    <div class="calculator-result" v-cloak>{{ result }}</div>
  </div>

    <div class="test">
      <div class="buttons">
        <div class="calc-button" @click="clear()">C</div>
        <div class="calc-button" @click="clearAll()">CE</div>
    </div>

    <div class="numbers">
      <div class="colOne">
        <div class="calc-number" @click="operate(7)">7</div>
        <div class="calc-number" @click="operate(4)">4</div>
        <div class="calc-number" @click="operate(1)">1</div>
      </div>

      <div class="colTwo">
        <div class="calc-number" @click="operate(8)">8</div>
        <div class="calc-number" @click="operate(5)">5</div>
        <div class="calc-number" @click="operate(2)">2</div>
        <div class="calc-number" @click="operate(0)">0</div>

      </div>

      <div class="colThree">
        <div class="calc-number" @click="operate(9)">9</div>
        <div class="calc-number" @click="operate(6)">6</div>
        <div class="calc-number" @click="operate(3)">3</div>
        <div class="calc-number" @click="operate('.')">.</div>
      </div>

      <div class="colfour">
        <div class="calc-button" @click="operate('/')">/</div>
        <div class="calc-button" @click="operate('*')">*</div>
        <div class="calc-button" @click="operate('-')">-</div>
        <div class="calc-button" @click="operate('+')">+</div>
        <div class="calc-button equal" @click="equal()">=</div>
      </div>
    </div>
  </div>
</div>

  </div>
</template>

<script>
export default {
  name: 'calculator',
  props: {
    msg: String
  },
  data () {
    return {
      title: 'Calculator',
      tal: '',
      result: 0
    }
  },
  methods: {
    operate(element) {
      this.tal += element;
    },
    equal() {
      // Take the result and do a calc. Eval calculates only on strings
        if (this.tal === '') {
          alert('Push a number!');
        } else {
          this.result = eval(this.tal);
        }
    },
    clearAll() {
      this.tal = '';
      this.result = '0';
    },
    clear() {
      this.tal = this.tal.slice(0, -1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  [v-cloak] {display: none;}

  .display {
    padding: 1rem;
    background: #999;
  }

  .calculator-formula {
    height: 1em;
  }

  .calculator-result, .calculator-formula {
    text-align: right;
    font-size: 1rem;
  }

  .calculator-result {
    font-size: 2rem;
  }

  .calculator {
    width: 450px;
    margin: auto;
    border: 2px solid #333;
  }

  .numbers, .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    padding: 1em;
  }

  .buttons {
    border-bottom: 1px solid #333;
  }

  .calc-number {
    padding: 1em;
    border: 1px solid #999;
    border-radius: 5px;
    margin: 5px;
    cursor: pointer;
  }

  .colfour {
    align-self: center;
  }

  .calc-button {
    padding: 1em;
    border: 1px solid #999;
    border-radius: 5px;
    margin: 5px;
    cursor: pointer;
  }

  .equal {
    border: 1px solid #999;
    border-radius: 2px;
  }
</style>
