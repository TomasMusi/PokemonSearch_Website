<!-- Autor: Tomáš Musil -->
<script>
	import { page } from '$app/stores';
</script>

<title>Error Page</title>

<div class="m-auto flex h-screen w-full flex-col justify-center">
	<img class="m-auto mb-2 flex h-auto w-1/3" src="/pepehands.png" alt="Pepe - Sad Face" />
	<h1 class="text-center text-6xl text-black">Oops Could't Find Page</h1>
	<div class=" m-auto mt-2 flex flex-row justify-center text-center">
		<h1 class=" text-4xl">
			{$page.status}:
		</h1>
		<h1 class="text-4xl text-red-500">{$page.error?.message}</h1>
	</div>
</div>
