<!-- Autor: Tomáš Musil -->
<script lang="ts">
</script>

<title>Úvodní Stránka Pokemon Search</title>

<!-- Navbar Container -->
<nav>
	<div class="flex h-16 w-full flex-row justify-center rounded-sm bg-blue-400">
		<div class="flex flex-row items-center justify-center gap-8">
			<a
				class="rounded-md text-2xl hover:bg-yellow-300 hover:p-3 hover:transition-all hover:duration-300"
				href="#">Domu</a
			>
			<a
				class="rounded-md text-2xl hover:bg-yellow-300 hover:p-3 hover:transition-all hover:duration-300"
				href="#">Ukazka</a
			>
			<button
				class="cursor-pointer rounded-lg bg-white p-4 hover:bg-slate-200 hover:transition-all hover:duration-300"
				><a href="#"></a>Search</button
			>
		</div>
	</div>
</nav>

<!-- HeroPage -->

<div class="relative flex">
	<img class="z-30 h-auto w-full brightness-50 filter" src="/pokemon.webp" alt="HeroPage - Fotka" />
	<div class="absolute z-50 flex h-full w-full flex-col items-center justify-center text-center">
		<h1 class="text-5xl font-black text-white">Pokemon Search</h1>
		<p class="mt-4 w-1/3 text-white">
			Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repellendus neque, quisquam ut rem,
			minus iusto alias exercitationem sed debitis reiciendis fugit sequi, excepturi vero incidunt
			veritatis delectus! Explicabo, numquam dolor!
		</p>
		<div class="mt-4 flex flex-row gap-4">
			<button
				class="rounded-md border border-solid border-red-400 bg-transparent p-4 font-medium text-white hover:scale-x-110 hover:border-blue-400 hover:transition-all hover:duration-300"
				>Vice Informací</button
			>
			<button
				class="rounded-md bg-red-400 p-4 pl-12 pr-12 font-medium text-white hover:scale-x-110 hover:bg-blue-400 hover:transition-all hover:duration-300"
				><a href="/PokemonSearch">Hledat</a></button
			>
		</div>
	</div>
</div>
