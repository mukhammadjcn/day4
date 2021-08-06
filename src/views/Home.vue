<template>
  <div class="home">
      <side-bar/>
      <div class="home__main">
        <div class="container row">
          <Header/>
          <navigation />
          <statistics />
          <div class="ariaChart">
            <area-chart />
          </div>
          <activity />
        </div>
      </div>
  </div>
</template>

<script>
import Activity from '../components/Activity.vue'
import AreaChart from '../components/AreaChart.vue'
import Header from '../components/Header.vue'
import Navigation from '../components/Navigation.vue'
import SideBar from '../components/SideBar.vue'
import Statistics from '../components/Statistics.vue'


export default {
  name: 'Home',
  components: { 
    Header,
    SideBar,
    Statistics,
    Activity,
    AreaChart,
    Navigation 
  },
  data(){
      return{
        chartData: {
          Books: 24,
          Magazine: 30,
          Newspapers: 10
        }
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;700;900&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-decoration-line: none;
  list-style-type: none;
  font-family: 'Lato', sans-serif;
}
.home{
  &__main{
    background: #F6F8FB;
    margin-left: 256px;
    transition: 0.2s ease-in-out;
    .container{
      flex-direction: column;
      gap: 30px;
    }
  }
}
.ariaChart{
  width: 100%;
  padding: 24px;
  background: white;
  border-radius: 8px;
}

@media (max-width:996px) {
  .home{
    &__main{
      margin-left: 0;
    }
  }
}
</style>
