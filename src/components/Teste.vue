<template>
    <div class="t" v-for="(pessoa, index) in list" v-bind:key="index">
        <div v-bind="idade">{{ pessoa.nome }} | {{ pessoa.idade }}</div>
    </div>
    <h1>{{ message }}</h1>
    <input type="text" v-model="message">
    <button v-on:click="showMessage(message)">Click aqui</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface Myobject {
    nome: string;
    idade: number;
}

const arr: Array<Myobject> = [
  { nome: 'Pedro', idade: 19 },
  { nome: 'Luiz', idade: 21 },
  { nome: 'Felipe', idade: 25 },
];

export default defineComponent({
  name: 'Teste',
  data() {
    return {
      list: arr,
      message: 'Hello world',
    };
  },
  methods: {
    showMessage(msg: string) {
      alert(msg);
    },
  },
});

</script>

<style scoped>
    .t {
        background: green;
    }
    .t div {
        color: black;
    }
</style>
