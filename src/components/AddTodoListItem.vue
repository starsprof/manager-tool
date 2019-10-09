<template>
  <div class="open-card-composer js-open-card-composer">
    <button>+</button>
    <input type="text" :value="value" v-on="listeners" placeholder="Добавить еще одну карточку" style="width: 200px">
  </div>
</template>

<script>
export default {
  name: 'AddTodoListItem',
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  computed: {
    listeners () {
      return {
        // Pass all component listeners directly to input
        ...this.$listeners,
        // Override input listener to work with v-model
        input: event => this.$emit('input', event.target.value)
      }
    }
  }
}
</script>

<style scoped>

</style>
