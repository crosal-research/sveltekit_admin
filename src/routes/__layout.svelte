<script context="module" lang="ts">
 import "../tailwind.css"
 import {logged} from "../stores"

 let islogged:bool = false
 
 
 function unsubscribe():void {
     logged.subscribe(value => 
 	 islogged = value)
 }

 export async function load({page}):void {
     unsubscribe()
     if (!islogged && page.path !="/"){
	 console.log(islogged)
	 return { 
		redirect: '/',
		status: '302'
		}
     }
     console.log(islogged)
     return { props: {} }
 }

</script>



<script lang="ts">
 import Nav from "../components/mainnav.svelte"
</script>

<div class="grid grid-cols-6 align-left gap-y-6">

    <!-- Upper stripe -->
    <div class="col-start-2 col-span-4 bg-blue-500 text-white text-center text-2xl rounded h-24 p-6">
	Admin Interface
    </div>

    <!-- Business interface -->
    <div class="col-start-2 col-span-4 border border-blue-500 p-4 rounded-lg">
	<Nav/>
	<slot></slot>
    </div>

</div>

<style>

</style>
