<script lang="ts">
	import { onMount } from 'svelte';
	import { animate, stagger } from 'motion';
	import { Coffee, Heart, Award, Sparkles } from '@lucide/svelte';
	import Background from '$lib/components/ui/background.svelte';

	let mounted = false;

	onMount(() => {
		mounted = true;
		// Simple animation after mount
		setTimeout(() => {
			const elements = document.querySelectorAll('.story-reveal');
			elements.forEach((el, i) => {
				(el as HTMLElement).style.opacity = '1';
				(el as HTMLElement).style.transform = 'translateY(0)';
			});
		}, 100);
	});

	const milestones = [
		{
			year: '2020',
			title: 'The Spark',
			description: 'A humble beginning in a small garage, fueled by a passion for perfect roasts.'
		},
		{
			year: '2022',
			title: 'Cloud Cafe Opens',
			description: 'We opened our doors to the community, serving airy pastries and robust coffee.'
		},
		{
			year: '2024',
			title: 'Award Winning',
			description: 'Recognized as the "Best New Cafe" for our signature Cloud Latte.'
		}
	];
</script>

<section id="story" class="relative overflow-hidden py-32 bg-[var(--bg)] text-[#2c2c2c] scroll-mt-20">
	<Background />

	<div class="relative z-10 mx-auto max-w-7xl px-8">
		<div class="grid gap-20 lg:grid-cols-2 lg:items-center">
			
			<!-- Left: Narrative -->
			<div class="space-y-8 text-left">
				<div class="story-reveal opacity-0 translate-y-5 transition-all duration-700 ease-out">
					<h2 class="mt-4 font-['Oswald'] text-5xl font-bold uppercase leading-none tracking-tighter md:text-7xl">
						More Than <br /> Just Coffee
					</h2>
				</div>

				<div class="story-reveal opacity-0 translate-y-5 transition-all duration-700 ease-out delay-100 space-y-6 text-lg leading-relaxed text-gray-600 relative p-4 lg:-mr-12">
					<p>
						 It started with a simple idea: coffee should feel like a pause in the clouds. 
						Away from the hustle, we wanted to create a sanctuary where the aroma of freshly ground beans 
						meets the lightness of steamed milk. 
					</p>
					<p>
						At Cloud Cafe, every cup tells a story of ethical sourcing, meticulous roasting, and 
						a barista's dedication to the craft. We don't just brew coffee; we curate moments of joy.
					</p>
				</div>

				<div class="story-reveal opacity-0 translate-y-5 transition-all duration-700 ease-out delay-200 flex gap-8 pt-4">
					<div class="flex flex-col items-center gap-2">
						<div class="flex h-14 w-14 items-center justify-center rounded-full border-2 border-[#2c2c2c] transition-transform hover:scale-110">
							<Coffee size={24} />
						</div>
						<span class="font-['Oswald'] text-xs font-bold uppercase tracking-widest">100% Arabica</span>
					</div>
					<div class="flex flex-col items-center gap-2">
						<div class="flex h-14 w-14 items-center justify-center rounded-full border-2 border-[#2c2c2c] transition-transform hover:scale-110">
							<Heart size={24} />
						</div>
						<span class="font-['Oswald'] text-xs font-bold uppercase tracking-widest">Handmade</span>
					</div>
					<div class="flex flex-col items-center gap-2">
						<div class="flex h-14 w-14 items-center justify-center rounded-full border-2 border-[#2c2c2c] transition-transform hover:scale-110">
							<Award size={24} />
						</div>
						<span class="font-['Oswald'] text-xs font-bold uppercase tracking-widest">Certified</span>
					</div>
				</div>
			</div>

			<!-- Right: Timeline/Visual -->
			<div class="pl-0 lg:pl-12">
				<div class="story-reveal opacity-0 translate-y-5 transition-all duration-700 ease-out delay-300 relative rounded-2xl border-2 border-dashed border-[#2c2c2c] p-8">
					
					<h3 class="mb-8 font-['Oswald'] text-2xl font-bold uppercase tracking-wide">Our Journey</h3>
					
					<div class="space-y-8 relative">
						<div class="absolute left-[7px] top-2 h-[85%] w-px bg-[#2c2c2c]/20"></div>
						
						{#each milestones as milestone}
							<div class="relative pl-8 group">
								<div class="absolute left-0 top-1.5 h-4 w-4 rounded-full border-2 border-[#2c2c2c] bg-[#FDFBF7] transition-colors group-hover:bg-[#2c2c2c]"></div>
								<span class="font-['Oswald'] text-sm font-bold text-amber-700">{milestone.year}</span>
								<h4 class="font-['Oswald'] text-xl font-bold uppercase">{milestone.title}</h4>
								<p class="mt-1 text-sm text-gray-600">{milestone.description}</p>
							</div>
						{/each}
					</div>
				</div>
			</div>

		</div>
	</div>
</section>
