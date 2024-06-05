<template>
  <div>
    <div class="flex">
      <div class="py-[40px] px-[40px]">
        <div class="w-[1100px] h-[500px] border border-black">
          <div class="flex justify-end w-full bg-red-700 pt-[18px] pr-[28px]">
            <div class="flex flex-col gap-[8px]">
              <div class="flex font-semibold text-[18px]">Start</div>
            </div>
          </div>
          <div class="w-[1100px] h-[420px] relative">
            <div
              class="w-[130px] h-[60px] absolute rounded-[6px] border border-black"
              :style="{ top: paddingTop + 'px', left: marginLeft + 'px' }"
            ></div>
          </div>
          <div class="pt-[10px] pl-[30px] font-semibold text-[18px] bg-red-700">
            End
          </div>
        </div>
      </div>
      <div
        class="w-[200px] mr-[14px] my-[230px] bg-sky-500 rounded-[16px] border border-black"
      >
        <div
          @click="moveTheBox('up')"
          class="flex justify-center py-[5px] mx-[60px] my-[15px] hover:scale-105 bg-green-600 border border-slate-200 text-white font-semibold cursor-pointer rounded-[6px]"
        >
          <div>Up</div>
        </div>
        <div class="p-[5px] flex justify-between px-[15px] mt-[10px]">
          <div
            @click="moveTheBox('left')"
            class="py-[5px] px-[10px] cursor-pointer bg-green-600 hover:scale-105 border border-slate-200 text-white font-semibold rounded-[6px]"
          >
            Left
          </div>
          <div
            @click="moveTheBox('right')"
            class="py-[5px] cursor-pointer bg-green-600 hover:scale-105 border border-slate-200 text-white font-semibold px-[10px] rounded-[6px]"
          >
            Right
          </div>
        </div>
        <div
          @click="moveTheBox('down')"
          class="flex justify-center py-[5px] cursor-pointer mx-[60px] my-[15px] rounded-[6px] hover:scale-105 bg-green-600 border border-slate-200 text-white font-semibold"
        >
          Down
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      paddingTop: 0,
      marginLeft: 970,
      topClass: "",
      leftClass: "",
    };
  },
  mounted() {
    this.moveTheBox("start");
  },
  methods: {
    moveTheBox(side) {
      if (side == "start") {
        console.log("skjd");
        this.topClass = `pt-[${this.paddingTop}px]`;
        this.leftClass = `ml-[${this.marginLeft}px]`;
      } else if (side == "up" && this.paddingTop - 40 >= 0) {
        console.log("usdj");
        this.paddingTop -= 40;
        this.moveTheBox("start");
      } else if (side == "down" && this.paddingTop < 336) {
        console.log("dsdj");
        this.paddingTop += 40;
        this.moveTheBox("start");
      } else if (side == "left" && this.marginLeft - 40 >= 0) {
        console.log("lsdj");
        this.marginLeft -= 40;
        this.moveTheBox("start");
      } else if (side == "right" && this.marginLeft <= 830) {
        console.log("rsdj");
        this.marginLeft += 40;
        this.moveTheBox("start");
      }
    },
  },
};
</script>
