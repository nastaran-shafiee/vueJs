<template>
  <h1>{{ msg }}</h1>
  <button @click.prevent.right="add(3, $event)"></button>
  <button @click.ctrl="add(5, $event)"></button>
  <input type="text" value="hi" @input="eventHandle" />
  <input type="text" v-model="model" />
  <p>{{ model }}</p>
  <h2>{{ count }}</h2>
  <p>{{ msg2 }}</p>
  <p v-text="model"></p>
  <div>
    <p v-for="(item, index) in arrayy" :key="index">{{ item }}</p>
  </div>
</template>

<script>
import { defineComponent, defineProps } from "vue";

export default defineComponent({
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
      msg2: "hi",
      arrayy: [1, 2, 3, 4],
      model: "yes",
    };
  },
  methods: {
    add(num, event) {
      console.log(event);
      return (this.count = this.count + num);
    },
    eventHandle(event) {
      console.log("hi");
      return (this.msg2 = event.target.value);
    },
  },
});
</script>
