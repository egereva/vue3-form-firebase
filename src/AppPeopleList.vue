<template>
  <div v-if="people.length !== 0">
    <div class="card inline" v-for="person in people" :key="person.id">
      <h3>
        {{ person.firstName }}
      </h3>
      <button class="btn danger" @click="$emit('remove', person.id)">Удалить</button>
    </div>
  </div>
  <div v-else class="card center">
    <h4>Людей пока нет</h4>
    <button class="btn" @click="$emit('load')">Загрузить список</button>
  </div>
</template>

<script>
export default {
  emits: ['load', 'remove'],
  props: ['people']
}
</script>

<style scoped>
  .inline {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
