<script  lang="ts">
 export let numberObs:string
</script>



<h1><strong>Observations</strong></h1>
<div class="flex flex-row gap-x-4">
    <div>
	<input class="my-2" type=radio bind:group={numberObs}  value="Last" /> Last
    </div>
    <div>
	<input class="my-2" type=radio bind:group={numberObs}  value="Last-10"/> 10-Last
    </div>
    <div>
	<input class="my-2" type=radio bind:group={numberObs}  value="All"/> All
    </div>
</div>
