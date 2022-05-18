<template>
  <li>
    <label>
      <input type="checkbox" v-model="finie" @input="$emit('change')" />
      <span :class="{ terminee: finie }">
        {{ todo.titre }}
      </span>
    </label>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    todo: Object,
  },
  data() {
    return {
      finie: this.todo.finie,
    };
  },
};
</script>

<style scoped>
.terminee {
  text-decoration: line-through;
}
li {
  list-style: none;
  flex-basis: 100%;
}
</style>
