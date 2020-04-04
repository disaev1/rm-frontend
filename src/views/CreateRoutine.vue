<template lang="pug">
div
  div Создание рутины
  b-field(label="Название")
    b-input(v-model="name")
  div
    div Выберите дни недели для выполнения
    b-checkbox(
      v-for="day in weekDays" v-model="checkedWeekDays" :native-value="day.id"
    ) {{ day.name }}
  b-button(@click="createRoutine" :disabled="!name") Создать рутину
</template>

<script>
import { weekDays } from '@/utils';

export default {
  name: 'CreateRoutine',
  data() {
    return {
      weekDays,
      name: null,
      checkedWeekDays: [],
    };
  },
  methods: {
    createRoutine() {
      console.log('name is', this.name);
      alert('Create routine ' + this.name);
    },
  },
};
</script>

<style scoped>

</style>
