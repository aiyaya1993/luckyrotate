<template>
  <!--<div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>-->
  <div id="app">
    <img src="./assets/rotate.jpeg" class="rotateImg" :style="{transform:rotate_angle_pointer,transition:rotate_transition_pointer}"/>
    <!--<img src="./assets/指针.png" :class="{'rotateImg1':flag1, 'rotateImg2':flag2, 'rotateImg3':flag}" @click="start"/>-->
    <img src="./assets/指针.png"  class="rotateImg3" @click="start">
  </div>
  <!--<div>-->
    <!--<canvas id="myCanvas" width="300" height="150" style="border:1px solid #d3d3d3;">-->
      <!--Your browser does not support the HTML5 canvas tag.-->
    <!--</canvas>-->
  <!--</div>-->
</template>

<script>
export default {
  name: 'App',
  data: function () {
    return {
      flag: 0,
      times: 0,
      rotate_angle_pointer: 'rotate(0deg)',
      rotate_transition_pointer: 'transform 2s ease-in-out'
    }
  },
  methods: {
    start: function () {
      // this.rotate_angle_pointer = `rotate(0deg)`
      if (this.flag === 0) {
        console.log(this.flag)
        this.rotate_angle_pointer = `rotate(${2 * 360 + Math.random() * 360}deg)`
        console.log(this.rotate_angle_pointer)
        this.times++
      }
      if (this.times > 5) {
        alert('您今天的抽奖次数已经用完')
        this.flag = 1
      }
    }
  }
  // mounted () {
  //   var c = document.getElementById('myCanvas')
  //   var ctx = c.getContext('2d')
  //   ctx.beginPath()
  //   ctx.arc(100, 75, 50, 0, 2 * Math.PI)
  //   ctx.stroke()
  // }
}
</script>

<style lang="scss">
/*#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
*{
  margin: 0;
  padding: 0;
}
.rotateImg {
  width: 400px;
  position: relative;
  z-index: -1;
}
.rotateImg1 {
  position: relative;
  top: -280px;
  left: 150px;
  width: 100px;
  animation:circleRoate 10s ;
  animation-timing-function:linear;
}
.rotateImg3 {
  position: relative;
  top: -280px;
  left: 150px;
  width: 100px;
  /*animation:circleRoate1 5s ;*/
  /*animation-timing-function:linear;*/
}
.rotateImg2 {
  position: relative;
  top: -280px;
  left: 150px;
  width: 100px;
}
@keyframes circleRoate{
  from{transform: rotate(0deg) infinite;}
  to{transform: rotate(720deg);}
}
@keyframes circleRoate1 {
  from{transform: rotate(0deg) infinite;}
  to{transform: rotate(200deg);}
}

</style>
