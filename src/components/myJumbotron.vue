  <script>
  import games from '../data/jumbo-db'
  export default {
  name: 'myJumbotron',
  data(){
    return {
      games,
      counter: 0,
    }
  }
  }
  </script>
<template>
  <div class="jumbotron">
    <img v-if="counter === 0" src="../assets/img/jumbo1.jpeg" alt="">
    <img v-if="counter === 1" src="../assets/img/jumbo2.jpeg" alt="">
    <div class="jumbo-container">
      <div class="stock">
        <span class="yellow-box">
          upcoming stock
        </span>
      </div>
      <div class="title">
        <span>{{ games[counter].title }}</span>
      </div>
      <div class="cta">
        <span>shop now</span>
      </div>
    </div>
    <div class="buttons d-flex justify-between">
      <div @click="this.counter--" class="prev"></div>
      <div @click="this.counter++" class="next"></div>
    </div>
  </div>
</template>


<style lang="scss" scoped>
@import '../scss/general/vars';
.jumbotron {
  // background-image: url(../assets/img/jumbo1.jpeg);
  background-size: cover;
  height: 550px;
  overflow: hidden;
  position: relative;
  img {
    width: 100%;
    object-fit: cover;
  }
}
.jumbo-container {
  width: 701px;
  padding: 170px 150px;
  margin-left: 80px;
  position: absolute;
  z-index: 998;
  left: 0;
  top: 0;
  div {
    margin: 10px 0;
  }
}
.stock {
  .yellow-box {
    display: inline-block;
    padding: 5px 25px;
    font-size: 18px;
    font-weight: 600;
  }
}
.title {
  span {
    font-size: 50px;
    padding: 0;
    line-height: 50px;
    margin-top: 20px;
    text-transform: capitalize;
  }
}
.cta {
  padding-top: 60px;
  span {
    font-size: 12px;
    
    padding: 5px 15px;
    background-color: white;
    color: black;
    cursor: pointer;
    margin-top: 20px;
  }
}
.cta:hover span {
  background-color: $secondary-color;
  transition: 1s;
}
.buttons {
  position: absolute;
  top: 50%;
  width: 100%;
  .prev, .next{
    cursor: pointer;
    width: 50px;
    height: 50px;
    background-repeat: no-repeat;
  }
  .prev {
    background-image: url(../assets/img/arrow.png);
    background-position: 0 -45px;
  }
  .next {
    background-image: url(../assets/img/arrow.png);
    background-position: right -45px;
  }
}


</style>