<script lang="ts">
 type navSide = "Surveys" | "Inflation" | "Tickers"
 let current:navSide = "Surveys"
</script>

<nav class="flex align-left w-ufll my-8 text-xl"> 
    <a class="subnavfocus" class:active="{current==='Surveys'}" 
       on:click="{() => current = 'Surveys'}" href="/update/">Surveys</a>
    <a class="subnavfocus" class:active="{current==='Inflation'}" 
       on:click="{() => current = 'Inflation'}" href="/update/inflation">Inflation</a>
    <a class="subnavfocus" class:active="{current==='Tickers'}" 
       on:click="{() => current = 'Tickers'}" href="/update/tickers">Tickers</a>
</nav>

<style>
 
 .active {
     /* @apply bg-blue-500 text-white; */
     @apply border-2 border-blue-500;
 }


</style>
