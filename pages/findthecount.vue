<template>
  <div class="p-[25px]">
    <div class="flex justify-between">
      <div>Find the count</div>
      <NuxtLink to="/">
        <diV
          class="px-3 py-3 rounded-[8px] text-white font-semibold bg-blue-600 hover:translate-y hover:scale-105 cursor-pointer"
          >Exit The Game</diV
        >
      </NuxtLink>
    </div>
    <div class="grid grid-cols-4 pt-[27px] w-full gap-[37px]">
      <div v-for="(item, index) of values" :key="index">
        <div class="bg-[#EEB0B0] h-[215px] rounded-[16px]">
          <div
            @click="getCircleCount(item)"
            class="grid grid-cols-5 py-[36px] px-[10px] gap-[24px] w-full"
          >
            <div
              v-for="rounds in item.circle"
              class="rounded-full bg-[#FF007A] h-[38px]"
            ></div>
          </div>
        </div>
        <div class="flex justify-between mt-[20px] gap-[5px]">
          <div v-if="!item.disable">
            <input
              v-model="item.userinput"
              placeholder="Enter The Count"
              class="w-[120%] p-[4px]"
            />
          </div>
          <div v-else>Your Ans : {{ item.userinput }}</div>

          <div
            v-if="item.userinput !== '' && !item.disable"
            @click="nextOuPut(item)"
            class="py-[2px] px-[8px] bg-blue-800 rounded-[4px] cursor-pointer flex items-center"
          >
            Submit
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
      values: [],
      circle: 0,
    };
  },
  mounted() {
    this.addBoxes();
  },

  methods: {
    addBoxes() {
      this.circle += 1;
      this.values.push({ circle: this.circle, userinput: "", disabled: false });
      console.log(this.values);
    },
    getCircleCount(item) {
      console.log(item.circle);
    },
    nextOuPut(item) {
      if (item.circle == item.userinput) {
        item.disable = true;
        this.addBoxes();
      } else if (item.circle != item.userinput) {
        alert("it's Wrong ");
      }
    },
  },
};
</script>
