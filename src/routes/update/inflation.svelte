<script lang="ts">
 import Obs from "../../components/observations.svelte"


 let inflation:string = "IPCA"

 type observations = "Last" | "Last-10" | "All"
 let obs:observations = "Last"


 function submit():void {
     console.log("submit inflation")
 }



</script>

<div class="flex justify-start">
    <div class="grid content-center grid-cols-2 ring-2 p-4">
	<div>
	    <input type=radio bind:group={inflation} value={"IPCA"} /> IPCA
	</div>
	<div>
	    <input type="radio" bind:group={inflation} value={"IPCA-15"} /> IPCA-15
	</div>
    </div>
</div>

	<!-- Observations -->
<div class="flex-row my-4">
    <Obs numberObs={obs} />
</div>
<div>
	<button class="btnsub" on:click={submit}>Submit</button>
    </div>

<style>
 .btnsub {
     @apply my-4 py-2 w-20 rounded bg-blue-500 text-white;
 }

</style>
