<script >
	import SinglePokemon from "$lib/components/single-pokemon.svelte";
    import { page } from "$app/stores";

    let pokemonId = $page.params.pokemonId;
    // console.log(pokemonId);
</script>

<div class="flex flex-col justify-center h-screen container">
    <SinglePokemon {pokemonId}/>
</div>