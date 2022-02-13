<script context="module" lang="ts">
	import "../scss/app.scss";
	export const prerender = true;
</script>
<script>
	import Navbar from './layout/Navbar.svelte';
	import Intro from './views/Intro.svelte';
	import Skills from './views/Skills.svelte';
	import Projects from './views/Projects.svelte';
	import WorkEducation from './views/WorkEducation.svelte';
	import Contact from './views/Contact.svelte';
	import Footer from './layout/Footer.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section class="min-h-screen bg-white dark:bg-slate-800">
	<div class="sticky top-0 z-10">
		<Navbar/>
	</div>
	<Intro/>
	<Skills/>
	<Projects/>
	<WorkEducation/>
	<Contact/>
</section>
<Footer/>


