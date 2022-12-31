<template>
  <div>
    <ul>
      <li v-for="classe of classes.data">
        <p> {{ classe.name }}</p>
        <img :src="classe.image" :alt="classe.name">
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data (){
    return {
      classes: []
    }
  },

  created() {
    let promise = this.$http.get('https://eldenring.fanapis.com/api/classes');
    promise.then(res => res.json().then(classes => this.classes = classes));
  }
}
</script>

<style>

</style>
