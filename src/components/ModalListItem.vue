<template>
  <div class="window-overlay" v-if="show">
    <div class="window">
      <div class="window-wrapper js-tab-parent">
        <button class="icon-md icon-close dialog-close-button js-close-window">x</button>
        <div class="card-detail-window">
          модальное окно
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalListItem',
  data: function () {
    return {
      show: true
    }
  }

}
</script>

<style scoped>
  .window-overlay {
    z-index: 1;
    position: absolute;
    background: rgba(87, 91, 113, 0.6);
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    cursor: pointer;
    display: none;
  }

  .window {
    position: absolute;
    background-color: white;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 5;
    border-radius: 6px;
    width: 500px;

  }

  .dialog-close-button {
    color: #42526e;
    border-radius: 50%;
    position: absolute;
    top: 0;
    right: 0;
    height: 32px;
    overflow: hidden;
    padding: 4px;
    margin: 4px;
    width: 32px;
    z-index: 2;
    transition: background-color 85ms, color 85ms;
  }

  .card-detail-window {
    min-height: 600px;
  }
</style>
