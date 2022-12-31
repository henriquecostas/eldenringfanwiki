<template>
  <div>
    <slot>
      <div class="class-panel">
        <h2 class="class-panel-title">{{ classTitle }}</h2>
        <img class="class-panel-image" :src="classImage" :alt="classDescription">
      </div>
  </slot>

  </div>
</template>

<script>
export default {
  props: ['classDescription', 'classImage', 'classTitle']
}
</script>

<style scoped>
  .class-panel{
    background: rgba(53, 52, 45, 0.777);
    width: 180px;
    height: auto;
    border-top-right-radius: 60px;
    border-top-left-radius: 20px;
    border-bottom-left-radius: 60px;
    padding: 4px 8px;
    margin: 20px;
    overflow: hidden;
  }

  .class-panel-list {
    list-style: none;
  }

  .class-panel-list .class-panel-list-item {
    display: inline-block;
  }

  .class-panel .class-panel-title {
    text-align: center;
    font-weight: 400;
    color: rgb(170 137 96);
  }

  .class-panel .class-panel-image {
    width: 90%;
    position: relative;
    top: 12px;
  }
</style>
