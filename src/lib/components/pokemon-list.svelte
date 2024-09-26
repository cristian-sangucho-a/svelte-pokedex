<script lang="ts">
    
    import PokemonCard from "$lib/components/pokemon-card.svelte";
	import { onMount } from "svelte";

    type Pokemon = {
        name: string;
        url: string;
    };

    let pokemons: Pokemon[] = []

    onMount(async()=>{
        const response = await fetch("https://pokeapi.co/api/v2/pokemon/?offset=20&limit=20");
        const data = await response.json();
        pokemons = data.results;
    })

</script>
<div class="grid grid-cols-12 gap-4 mt-8">
    {#each pokemons as pokemon}
        <PokemonCard name={pokemon.name} url={pokemon.url}/>
    {/each}
</div>

