<script lang="ts">
 import Obs from "../../components/observations.svelte"


 type survey = {
     name: string
     info: [string, string, string]
 }

 let surveys: survey[] =
     [{name:"BCB-Fiscal", info:["BCB", "FISCAL", "SERIES-TEMPORIAS"]}, 
 	 {name:"BCB-Credit", info:["BCB", "MERCADO-ABERTO",  "TITULOS-PUBLICOS"]}, 
 	 {name:"BCB-Externo", info:["BCB", "SETOR-EXTERNO",  "SERIES-TEMPORAIS"]}, 
 	 {name:"BCB-Econ", info:["BCB", "ECON",  "SERIES-TEMPORAIS"]},
	 {name: "BCB/ESTABILIDATE", info:  ["BCB", "ESTABILIDADE/FIN",  "SERIES-TEMPORAIS"]},
	 {name: "BCB/CAMBIO-CONTRATADO", info:  ["BCB", "CAMBIO-CONTRATADO",  "SERIES-TEMPORAIS"]},
	 {name:"VENC", info:["BCB", "TITULOS-PUBLICOS",  "SERIES-TEMPORAIS"]},
	 {name: "STN/RES-FISCAL", info:  ["STN", "RES-FISCAL",  "SERIES-TEMPORAIS"]},
	 {name: "RFB", info: ["RFB", "RES-ARRECADACAO", "SERIES-TEMPORAIS"]},
 	 {name:"IBGE-PIM", info:["IBGE", "PIM",  "SERIES-TEMPORAIS"]}, 
 	 {name:"IBGE-PMS", info:["IBGE", "PMS",  "SERIES-TEMPORAIS"]}, 
 	 {name:"IBGE-PMC",  info:["IBGE", "PMC", "SERIES-TEMPORAIS"]}, 
 	 {name:"IBGE-CN", info: ["IBGE", "CN",  "SERIES-TEMPORAIS"]},
	 {name: "PNAD", info:["IBGE", "PNAD",  "SERIES-TEMPORAIS"]},
	 {name:"CEPEA", info:["CEPEA", "AGRI", "SERIES-TEMPORAIS"]},
	 {name: "COMEX", info: ["COMEX", "ECON", "SERIES-TEMPORAIS"]},
	 {name: "IPEA/ECO", info: ["IPEA", "ECON", "SERIES-TEMPORAIS"]},
	 {name: "IPEA/FIN", info: ["IPEA", "FIN", "SERIES-TEMPORAIS"] },
 	 {name:"BEA-GDP", info:["BEA", "U.S. GDP", "SERIES-TEMPORAIS"]}, 
 	 {name:"BEA-SPENDING", info:["BEA", "U.S. PERSONAL CONSUMER-SPENDING", "SERIES-TEMPORAIS"]},
	 {name: "YAHOO/FUTURES", info:  ["YAHOO", "YAHOO-FUTURES",  "FINANCE"]},
	 {name: "FRED/FIN", info: ["FRED", "FRED-FIN", "FINANCE"]},
	 {name: "FRED/ECO", info: ["FRED", "ECON", "SERIES-TEMPORAIS"]}]

 let srs:string = "BCB-Fiscal"

 type observations = "Last" | "Last-10" | "All"
 let obs:observations = "Last"

 function submit():void {
     let s = surveys.filter((s) => s.name === srs)
     console.log(s[0].info)
     console.log(obs)
 }

</script>


<div class="flex">
    <div class="">
	<!-- Surveys -->
	<div class="grid grid-cols-3 gap-8">
	    <div>
		{#each surveys.slice(0,9) as survey}
		    <div class="my-1">
			<input type=radio bind:group={srs} value={survey.name} /> {survey.name}
		    </div>
		{/each}
	    </div>

	    <div>
		{#each surveys.slice(10,19) as survey}
		    <div class="my-1">
			<input type=radio bind:group={srs} value={survey.name} /> {survey.name}
		    </div>
		{/each}
	    </div>

	    <div>
		{#each surveys.slice(20, surveys.length) as survey}
		    <div class="my-1">
			<input type=radio bind:group={srs} value={survey.name} /> {survey.name}
		    </div>
		{/each}
	    </div>
	</div>

	<!-- Observation -->
	<div class="flex-row my-4">
	    <Obs numberObs={obs} />
	</div>

	<button class="btnsub" on:click={submit}>
	    Submit
	    <button/>

    </div>
</div>

<style>


</style>
