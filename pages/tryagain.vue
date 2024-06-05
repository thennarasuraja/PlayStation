<template>
       <div class="p-[40px]">
        <div>{{ value }}</div>
        <div @click="Increase()" v-bind:title="variable" class="felx bg-gray-700 w-[100px] rounded-[6px] text-white mt-[15px] p-[7px]"><button>Increase</button></div>
        <div @click="Decrease()" v-bind:title="'Decrease'" class="felx bg-gray-700 w-[100px] rounded-[6px] text-white mt-[20px] p-[7px]"><button>Decrease</button></div>
        <div v-bind:class="{'red':change}" class=" mt-[15px] w-[200px] h-[100px] bg-gray-700"></div> 

       </div>
</template>
<script>
export default{
  data(){
    return{
      value:0,
      jerry:"https://www.vuejs.org",
      variable:"increase value",
      change:true,
    }
  },
  methods:{
    Increase(){
      this.value++;
    },
    Decrease(){
      this.value--;
    }

  }
}
</script>
  
<!-- <template>
  <div>
    <div class="flex">
      <div class="py-[40px] px-[40px]">
        <div class="w-[1000px] h-[480px] border border-black">
          <div class="flex justify-end w-full bg-red-700 pt-[18px] pr-[28px]">
            <div class="flex flex-col gap-[8px]">
              <div class="flex font-semibold text-[18px]">Start</div>
            </div>
          </div>
          <div class="w-[1000px] h-[396px]" :class="topClass">
            <div
              class="w-[130px] h-[60px] rounded-[6px] border border-black"
              :class="leftClass"
            ></div>
          </div>

          <div class="pt-[10px] pl-[30px] font-semibold text-[18px] bg-red-700">
            End
          </div>
        </div>
      </div>
      <div class="w-[250px] my-[230px] border border-black">
        <div
          @click="moveTheBox('up')"
          class="flex justify-center py-[5px] mx-[100px] my-[15px] rounded-[6px] border border-black"
        >
          <div>Up</div>
        </div>
        <div class="p-[5px] flex justify-between px-[15px] mt-[10px]">
          <div
            @click="moveTheBox('left')"
            class="py-[5px] border border-black px-[10px] rounded-[6px]"
          >
            Left
          </div>
          <div class="py-[5px] border border-black px-[10px] rounded-[6px]">
            Right
          </div>
        </div>
        <div
          @click="moveTheBox('down')"
          class="flex justify-center py-[5px] mx-[100px] my-[15px] rounded-[6px] border border-black"
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
      marginLeft: 870,
      topClass: "",
      leftClass: "",
    };
  },
  mounted() {
    this.moveTheBox("start");
  },
  methods: {
    moveTheBox(side) {
      console.log("ujhewhuj");
      if (side == "start") {
        console.log("kuushdk");

        this.topClass = `pt-[${this.paddingTop}px]`;
        this.leftClass = `ml-[${this.marginLeft}px]`;
        console.log("kusdkh");
      } else if (side == "up") {
        console.log(this.paddingTop);
        this.paddingTop = this.paddingTop - 40;
        this.moveTheBox("start");
      } else if (side == "down") {
        console.log("kkgdsjhas");
        console.log(this.paddingTop);
        this.paddingTop = this.paddingTop + 40;
        this.moveTheBox("start");
      } else if (side == "left") {
        this.marginLeft = this.marginLeft - 40;
        console.log(this.marginLeft);
        this.leftClass = `ml-[${this.marginLeft}px]`;
        console.log("aksujd", this.leftClass);
      } else if (side == "right") {
        console.log(this.marginLeft);
        this.marginLeft = this.marginLeft - 40;
        this.leftClass = `ml-[${this.marginLeft}px]`;
        console.log("aksujd", this.leftClass);
      }
    },
  },
};
</script> -->
