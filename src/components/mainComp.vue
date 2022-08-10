<template>
  <div>
    <div>
      <div>
        <h1 class="text-green-700 font-black text-3xl">VUE CALCULATOR</h1>
      </div>
      <div class="flex items-center justify-center">
        <div class="item grid place-items-center h-10 w-72 bg-green-400">
          {{ current || 0 }}
        </div>
      </div>
    </div>

    <div class="space-x-4 space-y-4">
      <div></div>
      <button
        @click="clear()"
        class="bg-green-700 hover:bg-green-900 text-white font- py-3 px-5 rounded"
      >
        AC
      </button>
      <button
        @click="del()"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        Del
      </button>

      <button
        @click="multiply()"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        *
      </button>

      <button
        @click="append(' / ')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        /
      </button>

      <br />

      <button
        @click="append('7')"
        class="bg-green-700 hover:bg-green-900 text-white font- py-3 px-5 rounded"
      >
        7
      </button>
      <button
        @click="append('8')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        8
      </button>
      <button
        @click="append('9')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        9
      </button>
      <button
        @click="subtract()"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        -</button
      ><br />
      <button
        @click="append('4')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        4
      </button>
      <button
        @click="append('5')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        5
      </button>
      <button
        @click="append('6')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        6
      </button>
      <button
        @click="addition()"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        +</button
      ><br />
      <button
        @click="append('1')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        1
      </button>
      <button
        @click="append('2')"
        class="bg-green-700 hover:bg-green-9000 text-white font-bold py-3 px-5 rounded"
      >
        2
      </button>
      <button
        @click="append('3')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        3
      </button>
      <button
        @click="calc()"
        class="bg-green-700 hover:bg-green900 text-white font-bold py-3 text-center pb-10 px-5 rounded"
      >
        =</button
      ><br />
      <button
        @click="append('.')"
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-10 rounded"
      >
        .
      </button>
      <button
        class="bg-green-700 hover:bg-green-900 text-white font-bold py-3 px-5 rounded"
      >
        0</button
      ><br />
    </div>
  </div>
</template>

<script>
export default {
  name: "mainComp",
  data() {
    return {
      current: "",
      prev: "",
      new: "",
      opator: null,
      opratorclicked: false,
    };
  },
  methods: {
    clear() {
      this.current = "";
    },
    del() {
      this.current = this.current.slice(0, -1);
    },
    append(num) {
      if (this.opratorclicked) {
        this.current = "";
        this.opratorclicked = true;
      }
      this.current = `${this.current}${num}`;
    },
    addition() {
      this.opator = (a, b) => a + b;
      this.prev = this.current;
      this.opratorclicked = true;
    },
    subtract() {
      this.opator = (a, b) => a - b;
      this.prev = this.current;
      this.opratorclicked = true;
    },
    multiply() {
      this.opator = (a, b) => a * b;
      this.prev = this.current;
      this.opratorclicked = true;
    },
    divide() {
      this.opator = (a, b) => a / b;
      this.prev = this.current;
      this.opratorclicked = true;
    },

    calc() {
      this.current = `${this.opator(
        parseFloat(this.prev),
        parseFloat(this.current)
      )}`;
      this.prev = null;
    },
  },
};
</script>
