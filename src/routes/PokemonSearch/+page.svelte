<!-- Autor: Tomáš Musil -->
<script lang="ts">
	import { json } from '@sveltejs/kit';
	import Error from '../+error.svelte';

	let pokemon = $state<
		| {
				name: string;
				weight: number;
				height: number;
				sound: any;
				image: string;
		  }
		| undefined
	>(undefined);

	async function SearchPokemon(URL: string): Promise<any> {
		try {
			const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${URL.toLowerCase()}`);
			const data = await response.json();

			if (typeof data === "undefined") {
				console.log('Chyba');
			} else {
				pokemon = {
					name: data.name,
					weight: data.weight,
					height: data.height / 10,
					sound: data.cries.latest,
					image: data.sprites.front_default
				};
			}
		} catch (err) {
			console.error(`Nastala Chyba: ${err}`);
		}
	}
	let urlVal: string = $state('');
</script>

<title>Pokemon Searched: {pokemon?.name}</title>

<h1 class="mb-12 mt-5 text-center text-8xl">Pokemon Search</h1>

<div class="m-auto flex flex-row justify-center gap-1">
	<input
		bind:value={urlVal}
		class="w-1/4 justify-center rounded-md border border-solid border-black p-3 text-center"
		type="text"
		placeholder="Zadej Jméno Pokemona"
	/>

	<button
		onclick={() => {
			SearchPokemon(urlVal);
			console.log('Data se poslali!');
		}}
		class="cursor-pointer rounded bg-red-500 p-5 text-white hover:bg-red-700 hover:transition-all hover:duration-300"
		type="submit">Potvrdit</button
	>
</div>

<div
	class="m-auto mt-7 flex w-1/2 flex-col justify-center rounded-md bg-green-400 pt-7 text-center"
>
	<h1 class="text-5xl">Data</h1>
	<h1 class="text-2xl">Jméno {pokemon?.name}</h1>
	<h1>Hmotnost {pokemon?.weight}</h1>
	<h1>Velikost {pokemon?.height} M</h1>

	<img class="m-auto flex w-1/3" src={pokemon?.image} alt="" />
	<audio class="m-auto flex p-3" controls autoplay src={pokemon?.sound}></audio>
</div>
