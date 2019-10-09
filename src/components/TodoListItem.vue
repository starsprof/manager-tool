<template>
  <a class="list-card">
    <div class="list-card-details js-card-details">
      <span class="list-card-title js-card-name" v-on:click="isActive=!isActive" >{{todo.title}}</span>
      <button @click="$emit('remove', todo.id)">
        X
      </button>

    </div>
  </a>
</template>

<script>
export default {
  name: 'TodoListItem',
  props: {
    todo: {
      type: Object,
      required: true

    }
  },
  methods: {
    open: function () {
    }
  }
}
</script>

<style scoped>
  .list-card {
    background-color: #fff;
    border-radius: 3px;
    box-shadow: 0 1px 0 rgba(9,30,66,.25);
    cursor: pointer;
    display: block;
    margin-bottom: 8px;
    max-width: 300px;
    min-height: 20px;
    position: relative;
    text-decoration: none;
    z-index: 0;
  }
  .list-card-details {
    overflow: hidden;
    padding: 6px 8px 2px;
    position: relative;
    z-index: 10;
  }
  .list-card-title {
    clear: both;
    display: block;
    margin: 0 0 10px;
    overflow: hidden;
    text-decoration: none;
    word-wrap: break-word;
    color: #172b4d;
  }
</style>
