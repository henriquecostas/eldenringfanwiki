<template>
  <div>
    <div class="class-info-panel">
      <ul class="class-info-list">
        <li class="class-info-list-item" v-for="classe of classes.data">
          <class-panel 
            :className="classe.name" 
            :classTitle="classe.name"
            :classImage="classe.image"
            :classStats="classe.stats"
            :classStatsValue="classe.stats"
          > 
          </class-panel>
        </li>
      </ul>
    </div>
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

  html {
    height: 100%;
  }

  body {
    background: url('https://images8.alphacoders.com/118/1186452.jpg');
    background-size: cover;
    background-repeat: no-repeat;
  }

  .class-info-panel {
    background-color: #00000075;
    height: 620px;
    width: 50%;
    overflow: hidden;
    margin: 0 auto;
    border-radius: 20px;
  }

  .class-info-list{
    width: 100%;
    list-style: none; 
    margin: 0 auto;
    overflow-x: scroll;
    padding: 0;
  }
  
  .class-info-list-item{
    display: table-cell;
  }

</style>
