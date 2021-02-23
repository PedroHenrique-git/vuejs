<template>
    <div class="t" v-for="(pessoa, index) in list" v-bind:key="index">
        <div v-bind="idade" v-bind:id="index">{{ pessoa.nome }} | {{ pessoa.idade }}</div>
    </div>
    <h1>{{ message }}</h1>
    <input type="text" v-model="message">
    <input type="text" v-model="person">
    <button v-on:click="showMessage(message)">Click aqui</button>
    <button v-on:click="addPerson(person)">Click aqui para adicionar uma pessoa</button>
    <form v-on:submit.prevent="onSubmit()">
      <h1>Form</h1>
      <input class="ip1" type="text" v-model="val">
      <input type="submit" value="click here">
    </form>
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
      person: '',
      val: '',
    };
  },
  methods: {
    showMessage(msg: string): void {
      alert(msg);
    },
    addPerson(person: string): void {
      const pessoa = person.split(' ');
      this.list.push({ nome: pessoa[0], idade: Number(pessoa[1]) });
    },
    onSubmit() {
      if (this.val !== '') {
        alert('formulário enviado');
        return;
      }
      alert('Preencha o campo');
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
