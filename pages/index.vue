<template>
  <div>
   <div id="banner"><h2>RE-ACT-TIME</h2></div>
    <audio :src="require('@/assets/beep.mp3')"></audio>


    <timer/>


  </div>
</template>


<script type="text/javascript">
import timer from '~/components/timer.vue';
  export default{
    components:{  
      timer 
    }
  };
</script>

<style type="text/css">
body{
  /*height: 1000px;*/
  background-color: #34495e;
  color:white;
}
#banner{
  background-color: #130f40;
  height: 60px;
  align-items: center;
  display: flex;
  justify-content: center;
  /*border-bottom:solid #e74c3c 3px;*/
}
#banner h2{
  font-size: 30px;
}
</style>