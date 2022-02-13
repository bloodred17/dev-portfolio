<script lang="ts">
	interface TimelineItem {
		date: string;
		content: string;
		link: string;
	}
	const timeline: TimelineItem[] = [
		{
			date: 'Jan, 2019',
			content: 'First project, made for as bike rental startup in KIIT, Bhubaneshwar. (HTML, CSS)',
			link: 'https://kalingarider.netlify.app'
		},
		{
			date: 'Aug, 2019',
			content: 'Todo planner made in training bootcamp. (Vanilla Js)',
			link: 'https://todobr17.netlify.app'
		},
		{
			date: 'Aug, 2019',
			content: 'Wack-a-penguin game. The objective is to select penguins and stay away from Yeti and get the highest score. (Vanilla Js)',
			link: 'https://whackapenguinbr17.netlify.app'
		},
		{
			date: 'Sep, 2019',
			content: 'Test project made to learn API interaction. (Angular, Bootstrap)',
			link: 'https://digibartender.netlify.app/'
		},
		{
			date: 'Nov, 2019',
			content: 'Blog Manager as in Internship assignment from Shipthis. (Angular, Bootstrap)',
			link: 'https://litra-shipthis.netlify.app'
		},
		{
			date: 'Sep, 2020',
			content: 'Made the official website for the Alphabet Discord server. (Angular, Bootstrap)',
			link: 'https://alphabet-website.netlify.app'
		}
	];
</script>

<section id="projects" class="flex justify-center items-center py-12 md:py-32 bg-gradient-to-r from-blue-500 to-cyan-400 dark:from-stone-800 dark:to-gray-800">
	<div class="p-7 bg-[#eaf6ff] rounded-sm dark:bg-zinc-900 shadow-md">
		<h1 class="text-xl dark:text-gray-200"> Projects </h1>

		<ul class="mt-6">
			{#each timeline.reverse() as timelineItem}
			<li class="border-l-2 border-[#abaaed] border-dotted pb-6 pl-6 ml-1 relative
				before:content-[''] before:z-0 before:w-4 before:h-4 before:bg-white
				before:border before:border-[#4e5ed3] before:rounded-2xl before:rounded-2xl
				before:-left-2 before:top-0 before:absolute before:shadow
				last:z-0 last:border-0 last:pb-0
			">
				<div class="font-semibold dark:text-white">{timelineItem.date}</div>
				<p class="dark:text-gray-300 mt-1">{timelineItem.content}</p>
				<div class="mt-2 space-y-2 sm:space-y-0 sm:flex sm:-mx-1">
					<a href={timelineItem.link} target="_blank"
						class="flex items-center justify-center w-full px-2 py-1 text-white transition-colors duration-200 transform bg-blue-600 rounded-md focus:outline-none sm:w-auto sm:mx-1 hover:bg-blue-500 focus:bg-blue-500 focus:ring focus:ring-blue-300 focus:ring-opacity-40">
						<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"></path></svg>
						<span class="mx-1">
							View
            </span>
					</a>

					<div class="flex justify-end w-full gap-2">
						<button class="flex items-center justify-center w-full px-2 py-1 text-white transition-colors duration-200 transform bg-emerald-500 rounded-md focus:outline-none sm:w-auto sm:mx-1 hover:bg-emerald-600 focus:bg-emerald-600 focus:ring focus:ring-emerald-300 focus:ring-opacity-40">
							<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 10h4.764a2 2 0 011.789 2.894l-3.5 7A2 2 0 0115.263 21h-4.017c-.163 0-.326-.02-.485-.06L7 20m7-10V5a2 2 0 00-2-2h-.095c-.5 0-.905.405-.905.905 0 .714-.211 1.412-.608 2.006L7 11v9m7-10h-2M7 20H5a2 2 0 01-2-2v-6a2 2 0 012-2h2.5"></path></svg>
<!--							<span class="mx-1">-->
<!--								Like-->
<!--              </span>-->
						</button>

						<button class="flex items-center justify-center w-full px-2 py-1 text-white transition-colors duration-200 transform bg-red-500 rounded-md focus:outline-none sm:w-auto sm:mx-1 hover:bg-red-600 focus:bg-red-600 focus:ring focus:ring-red-300 focus:ring-opacity-40">
							<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14H5.236a2 2 0 01-1.789-2.894l3.5-7A2 2 0 018.736 3h4.018a2 2 0 01.485.06l3.76.94m-7 10v5a2 2 0 002 2h.096c.5 0 .905-.405.905-.904 0-.715.211-1.413.608-2.008L17 13V4m-7 10h2m5-10h2a2 2 0 012 2v6a2 2 0 01-2 2h-2.5"></path></svg>
<!--							<span class="mx-1">-->
<!--								Dislike-->
<!--              </span>-->
						</button>

					</div>
				</div>
			</li>
			{/each}
		</ul>
	</div>
</section>
