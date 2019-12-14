<template>
<div>
	<section class="hero is-success is-fullheight">
  <div class="hero-body">
    <div class="container">
      <h1 id="title" class="title">
        1 Minute Count Down
      </h1>
      <h2 id="timer" class="subtitle">
        {{time}}

      </h2>
      <button id="button" class="subtitle button is-danger is-light">Danger</button>
      
    </div>
  </div>
</section>



<!-- 
<div  class="container">
		<h3 class="center-align">1 Minute Count Down</h3>
		<h4>{{time}}</h4>
		<button v-bind:value="time"class="btn">Start</button> -->
</div>	
</template>


<script type="text/javascript">

const sleep = (ms) => {

  return new Promise(resolve => setTimeout(resolve, ms))
		}


	export default{
	data(){
		return{
			time: 3,
			iteration:1

		}
	},
	watch:{
		async iteration(){
			console.log('TRIG');
			await sleep(100)
			let audio = document.getElementsByTagName('audio')
			console.log(audio[0])
			// await sleep(1000000000)
			await audio[0].play()
			await sleep(2000)
			// this.$router.go()
		}
	},		
	async created(){
		let newtime = this.time
			for(var i =0; i<newtime;i++){
				await sleep(1000)
				console.log(`NOW NEW TIME: ${newtime}`)
				this.time -=1
				if(this.time == 0){
					console.log('END')
					this.time = newtime
					this.iteration +=1
					}
				}	
			
		}
		
	};
</script>

<style type="text/css" scoped>

#title{
	display: flex;
	justify-content: center;
}
.hero-body{
	flex-grow: 0;
}

#timer{
	display: flex;
	padding: 10px;
	justify-content: center;
}
.hero.is-success{
	background-color: #34495e;
}
#button{
	display: flex;
	justify-content: center;
	/*padding-top: 20px*/
}

</style>

