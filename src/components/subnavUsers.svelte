<script lang="ts">
 type navSide = "Search"
 let current:navSide = "Search"
</script>

<nav class="flex align-left w-ufll my-8 text-xl"> 
    <a class="subnavfocus" class:active="{current==='Search'}" 
       on:click="{() => current = 'Search'}" href="/users/">Search</a>
</nav>

<style>
 
 .active {
     @apply border-2 border-blue-500;
 }


</style>
