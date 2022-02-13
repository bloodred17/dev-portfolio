<script lang="ts">
	import { onMount } from 'svelte';

	type ThemeMode = 'light' | 'dark';
	let themeMode: ThemeMode;
	interface Route {
		name: string,
		link: string
	}
	const routes: Route[] = [
		{ name: 'me', link: '' },
		{ name: 'skills', link: '#skills' },
		{ name: 'projects', link: '#projects' },
		{ name: 'career', link: '#career' },
		{ name: 'contact', link: '#contact' },
	];

	let selected = 0;
	function selectLink(index: number) {
		selected = index;
	}
	// $: {console.log(selected)}

	let body;
	let career;

	onMount(() => {
		body = document.querySelector('body');
		career = document.querySelector('#career');

		if (localStorage.theme) {
			themeMode = (['light', 'dark'].includes(localStorage.theme)) ? localStorage.theme : 'dark';
		} else {
			themeMode = (window.matchMedia('(prefers-color-scheme: dark)').matches) ? 'dark' : 'light';
		}
		applyTheme(themeMode);
	});

	function applyTheme(mode: ThemeMode) {
		switch (mode) {
			case 'dark': remove('light'); add('dark'); break;
			case 'light': remove('dark'); add('light'); break;
		}
	}

	function toggleTheme(mode: 'light' | 'dark') {
		switch (mode) {
			case 'light': remove('light'); add('dark'); break;
			case 'dark': remove('dark'); add('light'); break;
		}
		themeMode = (mode === 'light') ? 'dark' : 'light';
		localStorage.theme = themeMode;
	}

	function add(classname: string) {
		body.classList.add(classname);
		career.classList.add(classname);
	}

	function remove(classname: string) {
		body.classList.remove(classname);
		career.classList.remove(classname);
	}
</script>

<nav class="container px-6 py-2 mx-auto lg:flex lg:justify-between lg:items-center backdrop-blur-md
bg-white/80 dark:bg-slate-900/80
">
	<div class="flex items-center justify-between">
		<div>
			<a class="text-xl text-gray-700 dark:text-white lg:text-2xl hover:text-gray-700 dark:hover:text-gray-300" href="/.">
				ankur<span class="text-blue-500">_</span>dutta
			</a>
		</div>

		<!-- Mobile menu button -->
		<div class="flex lg:hidden">
			<button type="button"
			        class="text-gray-500 hover:text-gray-600 focus:outline-none focus:text-gray-600"
			        aria-label="toggle menu">
				<svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
					<path fill-rule="evenodd"
					      d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z">
					</path>
				</svg>
			</button>
		</div>
	</div>

	<!-- Mobile Menu open: "block", Menu closed: "hidden" -->
	<div class="flex flex-col mt-4 space-y-2 lg:mt-0 lg:flex-row lg:-mx-6 lg:space-y-0">
		{#each routes as route, index}
			{#if route}
				<a href={route.link}
				   on:click={() => selectLink(index)}
				   class:border-blue-500={selected === index}
				   class:border-transparent={selected !== index}
				   class="text-gray-800 transition-colors duration-150 transform dark:text-gray-200
				   border-b-2 hover:border-pink-500
				   mx-1.5 sm:mx-6">{route.name}</a>
			{/if}
		{/each}
	</div>

	<button class="block h-10 px-5 py-2 mt-4 text-sm text-center text-gray-700 capitalize transition-colors duration-200 transform border rounded-md
	lg:mt-0 hover:bg-gray-100 lg:w-auto
	dark:hover:bg-gray-700 dark:text-white
	" on:click={() => toggleTheme(themeMode)}>
		{#if themeMode === 'dark'}
			<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"></path></svg>
		{:else}
			<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"></path></svg>
		{/if}
	</button>
</nav>
