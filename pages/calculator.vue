<template>
  <div class="flex justify-center">
    <div class="bg-slate-300 border border-slate-600 rounded-[16px] w-[500px]">
      <div class="py-[20px] px-[20px] flex flex-col gap-[15px]">
        <div class="flex justify-end bg-slate-400 border border-slate-500 rounded-[8px]">
          <div class="flex flex-col gap-[6px] py-[30px] px-[30px] h-[100px]">
            <div class="font-bold text-[16px]">
              <span v-if="expression.length == 0">0</span>
              {{ expression }}
            </div>
            <div class="text-[20px] font-bold text-white">
              <span v-if="result > 0">=</span>
              {{ result }}
            </div>
          </div>
        </div>

        <div class="border border-slate-500 rounded-[8px]">
          <div class="pt-[20px] px-[20px]">
            <div class="grid grid-cols-5 gap-[10px] w-full">
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('9')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="9">9</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('8')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="8">8</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('7')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="7">7</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('+')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="+">+</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('%')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="%">%</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('6')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="6">6</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('5')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="5">5</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('4')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="4">4</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('-')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="-">-</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('/')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="/">/</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('3')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="3">3</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('2')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="2">2</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('1')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py">1</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('0')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py">0</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="clearAll()"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py" value="c">AC</button>
                </div>
              </div>
            </div>
          </div>
          <div class="flex pt-[10px] gap-[10px] pb-[20px] px-[20px]">
            <div class="grid w-[250px] gap-[10px] grid-cols-3">
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('*')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py">*</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="sum('.')"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py">.</button>
                </div>
              </div>
              <div
                class="bg-slate-400 cursor-pointer border border-slate-500 rounded-[4px]"
                @click="backspace()"
              >
                <div class="flex justify-center py-[10px] px-[10px]">
                  <button class="text-center text-white py">x</button>
                </div>
              </div>
            </div>
            <div>
              <div class="grid w-[160px] grid-cols-1">
                <div
                  class="bg-orange-400 cursor-pointer border border-slate-500 rounded-[4px]"
                  @click="calculate()"
                >
                  <div class="flex justify-center py-[10px] px-[10px]">
                    <button class="text-center text-white py" value="=">=</button>
                  </div>
                </div>
              </div>
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
      expression: '',
      result: '',
    }
  },
  mounted() {},
  methods: {
    sum(button) {
      this.expression += button
    },
    calculate() {
      this.result = eval(this.expression)
    },
    clearAll() {
      this.expression = ''
      this.result = ''
    },
    backspace() {
      this.expression = this.expression.slice(0, -1)
    },
  },
}
</script>