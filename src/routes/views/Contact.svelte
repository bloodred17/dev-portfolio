<script lang="ts">

import Social from '../shared/Social.svelte';
</script>

<section id="contact" class="bg-stone-100 dark:bg-slate-800">
	<div class="container px-6 py-8 mx-auto">
		<div class="items-center lg:flex">
			<div class="lg:w-1/2 flex justify-center">

				<div>
					<h2 class="text-xl lg:text-2xl text-gray-800 dark:text-gray-100">Contact</h2>

					<p class="mt-4 text-gray-500 dark:text-gray-400 lg:max-w-md">
						I'm based in <a class="font-bold text-blue-600 dark:text-blue-400" href="https://www.google.com/maps/place/Bengaluru,+Karnataka/" target="_blank">Bangalore</a>
					</p>

					<p class="mt-4 text-gray-500 dark:text-gray-400 lg:max-w-md">
						email: <a class="font-bold text-blue-600 dark:text-blue-400" href="mailto:ankur.611@gmail.com">ankur.611@gmail.com</a>
					</p>

					<Social _class="flex items-center mt-6 -mx-2"/>

				</div>
			</div>

			<div class="mt-8 lg:mt-0 lg:w-1/2">
				<div class="flex items-center justify-center">
					<div class="max-w-lg">
						<iframe title="Bangalore"
							src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d497699.9973874144!2d77.35074421903857!3d12.95384772557775!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bae1670c9b44e6d%3A0xf8dfc3e8517e4fe0!2sBengaluru%2C%20Karnataka!5e0!3m2!1sen!2sin!4v1644594066450!5m2!1sen!2sin" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
