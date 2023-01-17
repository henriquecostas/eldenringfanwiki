<template>
  <div class="app">
    <div class="class-info-panel">
      <ul class="class-info-list">
        <li class="class-info-list-item" v-for="classe of filteredClasses">
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
    <div class="filter-container">
      <input
        class="filter" 
        type="search" 
        name="filter-list"
        placeholder="Type here to filter by class name"
        v-on:input="filterItem = $event.target.value" 
      />
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
      classes: [],
      filterItem: ''
    }
  },

  created() {
    this.$http.get('https://eldenring.fanapis.com/api/classes')
    .then(res => res.json())
    .then(classes => this.classes = classes.data, err => console.log(err));
  },

  computed: {
    filteredClasses() {

      if (this.filterItem) {
        let exp = new RegExp(this.filterItem.trim(), 'i');
        return this.classes.filter(classe => exp.test(classe.name));
      } else {
        return this.classes
      }
    }

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

  /* ===== Scrollbar CSS ===== */
  /* Firefox */
  * {
    scrollbar-width: auto;
    scrollbar-color: #a79d6c #393432;
  }

  /* Chrome, Edge, and Safari */
  *::-webkit-scrollbar {
    width: 4px;
  }

  *::-webkit-scrollbar-track {
    background: #393432;
  }

  *::-webkit-scrollbar-thumb {
    background-color: #a79d6c63;
    border-radius: 10px;
    border: 1px solid #585446;
  }

  .filter{
    width: 400px;
    margin-top: 20px;
    border: 1px solid rgb(36 35 31 / 90%);
    background-color: rgb(36 35 31 / 70%);
    color: #DCDCDC;
    border-radius: 8px;
    padding-left: 8px;
  }

  .filter-container{
    width: 50vh;
    margin: 0 auto;
    margin-top: 8px;
  }

</style>
