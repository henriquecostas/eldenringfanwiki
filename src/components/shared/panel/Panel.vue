<template>

    
      <div class="class-panel">
      <slot>  
          <h2 class="class-panel-title">{{ classTitle }}</h2>
          <img class="class-panel-image" :src="classImage">
        <div class="class-panel-stats">
          <table>
            <tr>
              <th scope="row">Level</th>
              <td style="text-align:center">{{ classStatsValue.level }}</td>
            </tr>
            <tr>
              <td>Vigor</td>
              <td style="text-align:center"> {{ classStatsValue.vigor }}</td>
            </tr>
            <tr>
              <td>Mind</td>
              <td style="text-align:center">{{ classStatsValue.mind }}</td>
            </tr>
            <tr>
              <td>Endurance</td>
              <td style="text-align:center">{{ classStatsValue.endurance }}</td>
            </tr>
            <tr>
              <td>Strength</td>
              <td style="text-align:center">{{ classStatsValue.strength }}</td>
            </tr>
            <tr>
              <td>Dexterity</td>
              <td style="text-align:center">{{ classStatsValue.dexterity }}</td>
            </tr>
            <tr>
              <td>Intelligence</td>
              <td style="text-align:center">{{ classStatsValue.intelligence }}</td>
            </tr>
            <tr>
              <td>Faith</td>
              <td style="text-align:center">{{ classStatsValue.faith }}</td>
            </tr>
            <tr>
              <td>Arcane</td>
              <td style="text-align:center">{{ classStatsValue.arcane }}</td>
            </tr> 
        </table>
        </div>
      </slot>
      </div>
</template>

<script>
export default {
  props: ['classImage', 'classTitle', 'classStats', 'classStatsValue']
}
</script>

<style scoped>
  .class-panel{
    background: rgb(19 18 14 / 85%);
    width: 180px;
    height: auto;
    border-top-right-radius: 60px;
    border-top-left-radius: 20px;
    border-bottom-left-radius: 20px;
    border-bottom-right-radius: 20px;
    padding: 4px 8px;
    margin: 20px;
  }

  .class-panel:hover{
    background: rgb(170 137 96 / 19%);
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
    border-bottom: 4px solid rgb(170 137 96);
    max-width: 80%;
    margin: 0 auto;
    padding: 12px 0 2px;
    font-size: 18px;
  }

  .class-panel .class-panel-image {
    width: 90%;
    position: relative;
    top: 12px;
    border-bottom-left-radius: 60px;
    border-bottom-right-radius: 60px;
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
  }


  .class-panel-stats table{
    width: 100%;
    box-sizing: border-box;
    margin: 20px 0px 12px;
    color: rgb(220, 220, 220);
    font-family: sans-serif;
    font-size: 14px;
    padding: 4px 2px;
  }
  .class-panel-stats th, td{
    background-color: rgb(36 35 31 / 44%);
  }

  .class-panel-stats td{
    margin: 20px 0px;
    padding: 4px 2px;
  }

</style>
