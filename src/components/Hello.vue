<template>
  <div class="hello">
      <div class="rubberBand" v-show='show'>
        <img src="../assets/logo.png">
        <p>{{msg}}</p>
      </div>
      <!-- <button @click='toggle'>toggle</button> -->
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Vue animation test',
      show:false,  
    }
  },
  mounted(){
    this.show = !this.show;
  },
  methods:{
    toggle(){
      this.show = !this.show;
    }    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*{padding: 0;margin: 0;}
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
@keyframes rubberBand {
  from {
    -webkit-transform: scale3d(1, 1, 1) ;
    transform: scale3d(1, 1, 1) ;
  }

  30% {
    -webkit-transform: scale3d(1.25, 0.75, 1) ;
    transform: scale3d(1.25, 0.75, 1) ;
  }

  40% {
    -webkit-transform: scale3d(0.75, 1.25, 1) ;
    transform: scale3d(0.75, 1.25, 1) ;
  }

  50% {
    -webkit-transform: scale3d(1.15, 0.85, 1);
    transform: scale3d(1.15, 0.85, 1) ;
  }

  65% {
    -webkit-transform: scale3d(.95, 1.05, 1);
    transform: scale3d(.95, 1.05, 1) ;
  }

  75% {
    -webkit-transform: scale3d(1.05, .95, 1);
    transform: scale3d(1.05, .95, 1) ;
  }

  to {
    -webkit-transform: scale3d(1, 1, 1) rotate(360deg);
    transform: scale3d(1, 1, 1) rotate(360deg);
  }
}
.rubberBand {
  -webkit-animation-name: rubberBand;
  animation-name: rubberBand;
  animation-duration: 1s;
}
</style>
