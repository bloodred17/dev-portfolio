<script lang="ts">
	const timelineStart = 2014;
	const timelineYears = (() => {
		const presentYear = +new Date().getFullYear();
		const years = [];
		let year = timelineStart;
		while (year <= presentYear) {
			years.push(year);
			year += 2;
		}
		return years;
	})();
	interface TimelineEvent {
		summary?: string,
		organisation?: string,
		designation?: string,
		class: string,
	}
	const timelineEvents: TimelineEvent[] = [
		{
			summary: 'High School',
			organisation: 'Kendriya Vidyalaya ONGC, Hazira',
			designation: 'Graduation',
			class: 'timeline-event-years-1 timeline-event-green elevate-1 timeline-start',
		},
		{
			class: 'timeline-event-years-1'
		},
		{
			summary: '2014-2019',
			organisation: 'KIIT University',
			designation: 'Bachelor, Electronics & Communication',
			class: 'timeline-event-years-5 timeline-event-orange elevate-2'
		},
		{
			summary: '2019-2020',
			organisation: 'Webstack Academy',
			designation: 'Bootcamp, MEAN Stack',
			class: 'timeline-event-years-1 timeline-event-blue elevate-3 max-w-xs'
		},
		{
			summary: '2020-Present',
			organisation: 'Shipthis Inc.',
			designation: 'Full Stack Developer',
			class: 'timeline-event-years-2 timeline-event-red elevate-4 timeline-end'
		},
	];
</script>


<section id="career"
         class="py-28 h-screen overflow-x-auto">
	<div class="flex justify-center">
		<h2 class="text-gray-200 text-lg">Career</h2>
	</div>

	<ul class="timeline-events">
		{#each timelineEvents as timelineEvent}
		<li class="{timelineEvent.class}">
			{#if timelineEvent.summary}
			<h2 class="text-gray-600 uppercase">{timelineEvent.summary}</h2>
			<h3 style="color: {timelineEvent.color}">{timelineEvent.organisation}</h3>
			<h4 class="text-gray-100 italic">{timelineEvent.designation}</h4>
			{/if}
		</li>
		{/each}
	</ul>

	<ul class="timelines-years">
		{#each timelineYears as year}
			<li>{year}</li>
		{/each}
	</ul>
</section>


<style lang="scss">
	@use "sass:math";

	// Variables
	// ----------------------------------------------
	$grid-background-color:             #0F0F0F;
	$grid-line-color:                   #000;
	$grid-width:                        100px;
	$timeline-events-no:                5;
	$timeline-events-line-height:       8px;
	$timeline-years-no:                 8;

	#career {
		//&.light {
		//	background-color: red;
		//}
		//background-image: linear-gradient(90deg, $grid-background-color 0, $grid-background-color $grid-width - 1, $grid-line-color $grid-width);
		background-size: $grid-width $grid-width;

		/* Timeline - Years */
		.timelines-years {
			position: relative;
			top: 300px;
			padding: 0 0 0 #{$grid-width * 2};
			margin: 0;
			white-space: nowrap;
			border-top: 1px solid #282828;
			list-style: none;
			font-size: 0;

			li {
				position: relative;
				top: -6px;
				display: inline-block;
				width: #{$grid-width * 2};
				color: #868686;
				font-size: 11px;
				line-height: 11px;
				text-indent: -12px;

				/* Display last year */
				&:last-child {
					width: $grid-width;
				}
			}
		}

		/* Timeline - Events */
		.timeline-events {
			position: relative;
			top: 170px;
			padding: 0;
			list-style: none;
			white-space: nowrap;
			font-size: 0;

			li {
				position: relative;
				display: inline-block;

				h2,
				h3,
				h4 {
					margin: 0 0 1px 0;
					font-weight: normal;
					font-size: 11px;
				}

				&:before {
					position: absolute;
					left: 0;
					bottom: -36px;
					height: $timeline-events-line-height;
					border-radius: $timeline-events-line-height;
					content: '';
				}
			}
		}

		@for $i from 1 through $timeline-events-no {
			.elevate-#{$i} {
				bottom: #{((($timeline-events-line-height * 2) * $i)) - ($timeline-events-line-height * 2)};
			}
		}

		.timeline-start {
			border-radius: 0 6px 6px 0;
		}
		.timeline-end {
			border-radius: 6px 0 0 6px;
		}

		$colors: (
			green: #C2E34E,
			orange: #FF9704,
			blue: #56C2F3,
			red: #DD3D01,
			aqua: #4A8B8F,
		);

		@each $name, $code in $colors {
			.timeline-events {
				li.timeline-event-#{"" + $name} {
					&:before {
						background: $code;
					}
					h3 {
						color: $code;
					}
				}
			}
		}

		/* Timeline - Events - Grid */
		@for $i from 0 through $timeline-years-no {
			/* X years */
			.timeline-event-years-#{$i},
			.timeline-event-years-#{$i}:before {
				width: #{$grid-width * $i};
			}
		}

	}

	//body.dark{
	//		margin-top: 1000px;
	//	//#career {
	//	//	//background-image: linear-gradient(90deg, $grid-background-color 0, $grid-background-color $grid-width - 1, $grid-line-color $grid-width);
	//	//	//background-color: red;
	//	//}
	//}


</style>
