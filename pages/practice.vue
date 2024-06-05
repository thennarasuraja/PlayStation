<template>
  <div class="flex justify-center">
    <div class="border border-black w-[500px] bg-slate-300 text-white p-[10px]">
      <div>
        <div
          class="flex flex-col p-8 border text-right border-slate-700 bg-slate-600 rounded-[6px] mx-[10px]"
        >
          <div>
            <span v-if="expression.length == 0">0</span> {{ expression }}
          </div>
          <div><span v-if="result > 0">=</span>{{ result }}</div>
        </div>
      </div>
      <div class="m-[10px] border border-slate-800">
        <div class="grid grid-cols-5 text-white mt-[10px]">
          <div
            @click="display('9')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="9"
          >
            9
          </div>
          <div
            @click="display('8')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="8"
          >
            8
          </div>
          <div
            @click="display('7')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="7"
          >
            7
          </div>
          <div
            @click="display('+')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="+"
          >
            +
          </div>
          <div
            @click="display('%')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="%"
          >
            %
          </div>
          <div
            @click="display('6')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="6"
          >
            6
          </div>
          <div
            @click="display('5')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="5"
          >
            5
          </div>
          <div
            @click="display('4')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="4"
          >
            4
          </div>
          <div
            @click="display('-')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="-"
          >
            -
          </div>
          <div
            @click="display('/')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="/"
          >
            /
          </div>
          <div
            @click="display('3')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="3"
          >
            3
          </div>
          <div
            @click="display('2')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="2"
          >
            2
          </div>
          <div
            @click="display('1')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="1"
          >
            1
          </div>
          <div
            @click="display('*')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="*"
          >
            *
          </div>
          <div
            @click="clearAll()"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
          >
            AC
          </div>
          <div
            @click="display('0')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
            value="0"
          >
            0
          </div>
          <div
            @click="display('.')"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
          >
            .
          </div>
          <div
            @click="clear()"
            class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold mx-[10px] my-[10px] bg-slate-600"
          >
            x
          </div>
          <div class="grid w-[180px] grid-cols-1">
            <div
              @click="Equal()"
              class="flex justify-center cursor-pointer rounded-[4px] p-[5px] font-bold text-2xl mx-[10px] my-[10px] bg-red-600"
              value
            >
              =
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      expression: "",
      result: "",
    };
  },
  methods: {
    display(sum) {
      this.expression += sum;
    },

    clear() {
      this.expression = this.expression.slice(0, -1);
    },
    Equal() {
      this.result = eval(this.expression);
      console.log(this.result);
    },
    clearAll() {
      this.expression = "";
      this.result = "";
    },
  },
};
</script>
