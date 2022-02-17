<template>
  <div class="skills h-auto overflow-hidden bg-gray-600">
    <div class="square xyz-in" xyz="fade duration-6 delay-2 up-100%">
      <Title
        class="title text-gray-100"
        :title="'Works'"
        :description="'Some of my works'"
      />
    </div>

    <div
      class="flex flex-wrap items-center px-auto mx-auto justify-center"
      xyz="fade small stagger-0.5"
    >
      <div
        class="card p-1 mb-2 xyz-in"
        v-for="(work, index) in works"
        :key="index"
      >
        <div class="xyz-in">
            <img
              class="
                img
                h-72
                w-auto
                m-8
                cursor-pointer
                rounded-md
                duration-500
                transform
                -translate-y-2
                hover:translate-y-0
                ease-in-out
              "
              :src="require(`../assets/img/lem/${work.filename}`)"
              alt="image"
            />
          <h1 class="name text-gray-100 font-semibold text-xs text-center mt-0">
            {{ work.name }}
          </h1>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Title from "./Title.vue";
// import git from "../assets/img/logos/git.svg"
// const loc = '../assets/img/logos/'
import { ref, watch } from "vue";
export default {
  name: "Works",
  setup() {
    const xyz = ref("");
    const animationIndex = ref(-1);
    watch(animationIndex, (newValue) => {
      if (newValue > -1)
        xyz.value = "duration-20 ease-in-out-back small iterate-infinite";
      console.log(newValue);
    });
    return {
      xyz,
      animationIndex,
    };
  },
  components: {
    Title,
  },
  methods: {
    openTab: function (item) {
      window.open("http://192.168.0.59:8081/img/" + item);
    },
  },
  props: ["works"],
};
</script>