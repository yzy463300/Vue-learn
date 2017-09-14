<template>
  <div class="transition-demo1">
    <!-- transition -->
    <transition name='fadeIn'>
      <p class="title" v-if="show">wxCat</p>
    </transition>
    <!-- animation -->
    <transition name='bounce'>
        <p v-if="show">Look at me!</p>
    </transition> 
    <!-- 通过自定义类名 -->
    <transition
      name='custom-classes-transition'
      enter-active-class='animated bounce'
      leave-active-class='animated bounce'
    >
      <h1 v-if='show'>Are You Ready?</h1>
    </transition>
    <button @click="toggle">toggle</button>    
  </div>
</template>

<script>
export default {
  name: 'transition1',
  data () {
    return {
      msg: 'Vue animation test',
      show:false, 
    }
  },
  mounted(el){
    console.log(el)
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
  font-size: 100px;
  color: #41b883;
}

ul {
  list-style-type: none;
  padding: 0;
  font-size: 20px;
}

li {
  display: inline-block;
  margin: 0 10px;
}
p{
  font-size: 50px;
}
a {
  color: #42b983;
}
.title{
  font-size: 200px;
  font-weight: bold;
  color: #35495e;

}
/*在元素整个过渡过程中作用，在元素被插入时生效，在transition/animation完成后移除*/
.fadeIn-enter-to{

}
.fadeIn-enter-active,.fadeIn-leave-active{
  transition:all 1s;
}
/*进入过渡的开始状态，在元素被插入时生效，在下一帧移除*/
.fadeIn-enter,.fadeIn-leave-to{
  opacity: 0;
}

.bounce-enter-active{
  animation:bounce-in .5s;
}
.bounce-leave-active{
  animation:bounce-in .5s reverse;
}
@keyframes bounce-in{
  0%{
    transform:scale(0);
  }
  50%{
    transform:scale(1.5);
  }
  100%{
    transform:scale(1);
  }
}
.bounce-in{
  animation-name:bounce-in;
}



</style>
