<script lang="ts">
 import Obs from "../../components/observations.svelte"

 type observations = "Last" | "Last-10" | "All"
 let obs:observations = "Last"


 function submit():void {
     console.log("submit tickers")
 }
 
</script>

<div class="flex-row justify-start">

	<div  class="my-8">
	    <input placeholder="Ticker" class="w-500 h-10 ring-2" />
	</div>
	<div>
	    <button class="btnsub" on:click={submit}>Submit</button>
	</div>

		<!-- Observations -->
	<div class="flex-row my-4">
	    <Obs numberObs={obs} />
	</div>

</div>	

<style>

 .btnsub {
     @apply my-1 py-2 w-20 rounded bg-blue-400 text-white;
 }


</style>
