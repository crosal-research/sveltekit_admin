<script lang="ts">
 import User from "../../components/user.svelte"
 
 type userInfo = {
     name:string
     username:string
     institution:string
 }


 let users:userInfo[] = [
     {
	 name: "admin",
	 username: "admin",
	 institution: "any",
     },
     {
	 name: "admin",
	 username: "admin",
	 institution: "any",
     }]

</script>


<div class="flex">
    <div class="grid grid-cols-1">
	<h1 class="text-xl"><strong>Users</strong></h1>
	{#each users as user}
	    <User {...user}/>
	{/each}    
    </div>
</div>
