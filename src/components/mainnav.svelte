<script lang="ts">
 import {logged, currentPage} from "../stores"


 function loggout():void {
     logged.set(false)
     currentPage.set('Home')
 }

 
</script>

{#if $logged}
    
<nav class="flex justify-center w-ufll 
	    my-4 text-xl justify-items-center">
    <a class="navfocus" class:active="{$currentPage==='Update'}" 
       on:click="{() => currentPage.set('Update')}" href="/update/">Data</a>
    <a class="navfocus" class:active="{$currentPage==='Users'}" 
       on:click="{() => currentPage.set('Users')}" href="/users/">Users</a>
    <a class="navfocus" class:active="{$currentPage==='Home'}"
       on:click="{() => loggout()}" href="/">LogOut</a>
</nav>

{/if}

<style>
 
 .active {
     @apply border-2 border-blue-500;
 }

</style>
