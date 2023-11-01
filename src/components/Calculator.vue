<template>
  <div id="app">
    <input v-model="hasil" type="text">
    <button @click="clear">C</button>
    <button @click="calculate">=</button>

    <div class="buttons">
      <button @click="appendToResult('7')">7</button>
      <button @click="appendToResult('8')">8</button>
      <button @click="appendToResult('9')">9</button>
      <button @click="appendToResult('/')" data-operator>÷</button>

      <button @click="appendToResult('4')">4</button>
      <button @click="appendToResult('5')">5</button>
      <button @click="appendToResult('6')">6</button>
      <button @click="appendToResult('*')" data-operator>×</button>

      <button @click="appendToResult('1')">1</button>
      <button @click="appendToResult('2')">2</button>
      <button @click="appendToResult('3')">3</button>
      <button @click="appendToResult('+')" data-operator>+</button>

      <button @click="appendToResult('0')">0</button>
      <button @click="appendToResult('.')">.</button>
      <button @click="appendToResult('-')">-</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      hasil: "",
    };
  },
  methods: {
    clear() {
      this.hasil = "";
    },
    calculate() {
      try {
        this.hasil = eval(this.hasil);
      } catch (error) {
        this.hasil = "Error";
      }
    },
    appendToResult(value) {
      this.hasil += value;
    },
  },
};
</script>

<style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        #app {
            background-color: #fff;
            border: 1px solid #ccc;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            border-radius: 5px;
            padding: 20px;
            width: 300px;
        }

        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            font-size: 20px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }

        button {
            width: 50px;
            height: 50px;
            font-size: 20px;
            margin: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
            cursor: pointer;
            background-color: #f0f0f0;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #ccc;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 5px;
        }

        /* Style the operators (+, -, *, /) differently */
        button[data-operator] {
            background-color: #ff8c00; /* Orange */
        }

        button[data-operator]:hover {
            background-color: #ff9900; /* Darker Orange */
        }
    </style>
    
    
    
   