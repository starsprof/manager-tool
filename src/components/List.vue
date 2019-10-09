<template>
  <div class="list-wrapper">
    <div class="list">
      <div class="list-header">
        <div class="list-header-name">
            {{title }}
        </div>
      </div>
    <TodoList/>
    </div>
  </div>
</template>

<script>
import TodoList from './TodoList'

export default {
  name: 'List',
  components: { TodoList }
}
</script>

<style scoped>
  .list-wrapper {
    width: 272px;
    margin: 0 4px;
    height: 100%;
    box-sizing: border-box;
    display: inline-block;
    vertical-align: top;
    white-space: nowrap;
  }

  .list {
    background-color: #ebecf0;
    border-radius: 3px;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    max-height: 100%;
    position: relative;
    white-space: normal;
  }
  .list-header {
    flex: 0 0 auto;
    padding: 10px 8px;
    position: relative;
    min-height: 20px;
  }

</style>
