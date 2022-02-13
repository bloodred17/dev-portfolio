<script lang="ts">
import HighlightText from '../shared/HighlightText.svelte';
</script>

<div class="lg:flex dark:bg-slate-800">
	<div class="flex items-center justify-center w-full px-6 py-8 lg:w-1/2">
		<div class="max-w-xl">
			<h2 class="text-2xl font-semibold text-gray-800 dark:text-white lg:text-3xl">Full Stack <span class="text-blue-600 dark:text-blue-400">Developer</span></h2>

			<p class="mt-2 text-sm text-gray-500 dark:text-gray-400 lg:text-base">
				Hi, I'm Ankur, I <HighlightText text={'love to code'}/> and build <HighlightText text={'applications'}/> that <HighlightText text={'solve problems'}/>.
			</p>

			<p class="mt-2 text-sm text-gray-500 dark:text-gray-400 lg:text-base">
				Currently working as a software developer <a href="https://shipthis.co" target="_blank">@<HighlightText text={"ShipThis"}/></a>.
			</p>

		</div>
	</div>

	<div class="hidden sm:block w-full lg:w-1/2" style="height: 90vh;">
		<div class="w-full h-full bg-cover"
		     style="background-image: url(https://images.unsplash.com/photo-1508394522741-82ac9c15ba69?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=748&q=80)">
		</div>
	</div>
</div>
