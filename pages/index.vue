<template>
  <div
    class="flex min-h-screen items-center justify-center bg-gradient-to-tr to-blue-400 from-green-500 p-10"
  >
    <div
      class="grid grid-cols-3 gap-[40px] w-full h-screen px-[80px] py-[110px]"
    >
      <div
        class="bg-white w-full h-[80%] hover:-translate-y-2 hover:scale-110 rounded-[20px] cursor-pointer"
        v-for="(game, index) in games"
        :key="index"
      >
        <nuxt-link :to="game.path">
          <div class="w-full bg-slate-50">
            <img :src="game.image" class="w-full h-[240px]" />
          </div>
          <div
            class="w-full h-[40%] flex justify-center items-center font-sans font-semibold text-slate-950 text-[30px]"
          >
            {{ game.name }}
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      games: [
        {
          name: "Find The Count",
          path: "/findthecount",
          image:
            "https://cdn.splashmath.com/curriculum_uploads/images/playables/count_comp_hide_and_seek_10_gm.png",
        },
        {
          name: "Find The Path",
          path: "/boxgame",
          image:
            "https://coherent-labs.com/wp-content/uploads/2018/01/V2_Animation_no_path_gif.gif",
        },
        {
          name: "Calculate The Numbers",
          path: "/calculator",
          image:
            "https://cdn.dribbble.com/users/2004171/screenshots/5646149/dribbble_canvas__calculator_.gif",
        },
      ],
    };
  },
};
</script>

<!-- 
<template>
  <div class="p-[60px]">
    <div class="flex justify-between items-center">
      <div>BOXES</div>
      <div @click="jerry()" class="w-[100px] h-[40px] bg-blue-600 cursor-pointer flex justify-center items-center rounded-[16px] ">Create boxes</div>
    </div>
    <div class="pt-[50px] grid grid-cols-3 gap-[40px]">
      <div v-for="items in variable.length" class="w-[380px] h-[200px] bg-gray-600 rounded-[16px]"></div>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return{
      variable:[]
    }
  },
  methods:{
    jerry(){
      this.variable.push({})
    }
  }
}

</script> -->
