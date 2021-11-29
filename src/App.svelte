<svelte:options tag="simple-clock" />
<script>
	import {onMount} from "svelte";
	export let size=15;
	let now = new Date();
	let out=`00:00:00`;
	function dd(num){
		return num<10 ? `0${num}`:num;
	}
	onMount(()=>{
		setInterval(function(){
			now = new Date();
			out=`${dd(now.getHours())}:\
            ${dd(now.getMinutes())}:\
            ${dd(now.getSeconds())}`;
	  }, 500);
	})
</script>
<div class="clock" style="font-size:{size}px;">{out}</div>
<style>
  .clock {
    border: 5px solid green;
    border-radius: 10px;
    font-weight: bold;
    display: inline-block;
    padding: 5px;
  }
</style>
