<template>
    <div class='d1'>
        <h1>{{ cout }}</h1>
    </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Couter',
  props: {
    msg: String,
  },
  data() {
    return {
      cout: 0,
    };
  },
  mounted() {
    setInterval(() => {
      this.cout += 1;
    }, 1000);
  },
});
</script>

<style scoped>
    .d1 {
        background: red;
        width: 50vw;
        margin: 0 auto;
    }

    .d1 h1 {
        color: black;
    }
</style>
