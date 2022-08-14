<template>
  <div class="home">
    <h1>composition api and Script setup</h1>
    <p>
      Hi my name is <b>{{ name }}</b> and I am <b>{{ age }}</b> years old
    </p>
    <h4 class="h4">
      she name's {{ datas.sophal }}, she's major is {{ datas.position }}
    </h4>
    <p style="color: red">
      <i>{{ compute }}</i>
    </p>
    <input type="text" placeholder="enter ur name" v-model="n" />
    <button @click="clickBtn">Add+</button>
    <h1 v-for="inputVal in storeN" :key="inputVal">{{ inputVal }}</h1>
  </div>
</template>



 <!-- ================================== @ Composition api =============================================-->

<!-- <script>
import { computed, ref } from "vue";

//setup function is run before other function event if mounted
//use it to hold the option aip such as data, methods, computed...
//can't use "this" to call each variable
export default {
  setup() {
    console.log("setup");
    let name = "sophal";
    let age = 22;
    //we use ref to create reactive
    let n = ref(null);
    let storeN = ref([]);
    //
    let example = ref(null);
    let sampleValue = ref("Hi from computed");
    //
    let datas = ref({ sophal: "sophal sararn", position: "web developer" });
    //
    const clickBtn = () => {
      storeN.value.push(n.value);
      n.value = "";
    };
    const compute = computed(() => {
      example = sampleValue.value;
      return example;
    });
    //all var & function need to return
    return {
      name,
      age,
      n,
      storeN,
      datas,
      clickBtn,
      compute,
    };
  },
};
</script> -->


<!-- ====================================== @Script setup =============================================-->

<!-- If use script setup
- Don't need to export default class,
- Don't need to set up Api
 -->
 <script setup>
import { computed, ref } from "vue";

console.log("setup");
let name = "sophal";
let age = 22;
//we use ref to create reactive
let n = ref(null);
let storeN = ref([]);
//
let example = ref(null);
let sampleValue = ref("Hi from computed");
//
let datas = ref({ sophal: "sophal sararn", position: "web developer" });
//
const clickBtn = () => {
  storeN.value.push(n.value);
  n.value = "";
};
const compute = computed(() => {
  example = sampleValue.value;
  return example;
});
</script>
