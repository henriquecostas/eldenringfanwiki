<template>
  <div>
    <ul>
      <li v-for="classe of classes.data">
        <class-panel 
          :className="classe.name" 
          :classTitle="classe.name"
          :classImage="classe.image"
        > 
        </class-panel>
      </li>
    </ul>
  </div>
</template>

<script>
import Panel from './components/shared/panel/Panel.vue';

export default {
  components:{
    'class-panel': Panel
  },

  data (){
    return {
      classes: []
    }
  },

  created() {
    this.$http.get('https://eldenring.fanapis.com/api/classes')
    .then(res => res.json())
    .then(classes => this.classes = classes, err => console.log(err));
  }
}
</script>

<style>

  body {
    background: url('https://images8.alphacoders.com/118/1186452.jpg');
    background-repeat: no-repeat;
    background-size: cover;
  }

</style>
