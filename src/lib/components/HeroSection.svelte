<script lang="ts">
	import { onMount } from 'svelte';
	import { animate, stagger } from 'motion';
	import { ArrowDown, Cloud } from '@lucide/svelte';

	onMount(() => {
		animate(
			'.hero-element',
			{ opacity: [0, 1], y: [20, 0] },
			{ 
				duration: 0.8, 
				delay: stagger(0.2),
				easing: [0.22, 0.03, 0.26, 1] 
			}
		);
	});

	function scrollToMenu() {
		const menuElement = document.getElementById('menu');
		if (menuElement) {
			menuElement.scrollIntoView({ behavior: 'smooth' });
		}
	}
</script>

<section class="relative flex min-h-screen flex-col items-center justify-center overflow-hidden bg-[var(--bg)] px-4 py-20 text-center font-sans text-[#2c2c2c]">
	<!-- Background decoration (abstract cloud shapes) - Subtle approximation of the line art -->
    <div class="absolute inset-0 pointer-events-none opacity-10">
        <svg class="absolute top-10 left-10 w-32 h-32 md:w-64 md:h-64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="0.5">
             <path d="M17.5 19c0-1.7-1.3-3-3-3h-11c-1.7 0-3-1.3-3-3s1.3-3 3-3c.4 0 .7.1 1 .2 0-2.8 2.2-5 5-5 2.4 0 4.4 1.7 4.9 4 .3-.1.7-.2 1.1-.2 1.7 0 3 1.3 3 3 .6 0 1.1.1 1.5.4 1.3.9 2 2.3 2 4s-1.8 3.5-3.5 3.5z"></path>
        </svg>
        <svg class="absolute bottom-10 right-10 w-40 h-40 md:w-80 md:h-80" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="0.5">
             <path d="M17.5 19c0-1.7-1.3-3-3-3h-11c-1.7 0-3-1.3-3-3s1.3-3 3-3c.4 0 .7.1 1 .2 0-2.8 2.2-5 5-5 2.4 0 4.4 1.7 4.9 4 .3-.1.7-.2 1.1-.2 1.7 0 3 1.3 3 3 .6 0 1.1.1 1.5.4 1.3.9 2 2.3 2 4s-1.8 3.5-3.5 3.5z"></path>
        </svg>
    </div>

	<!-- Content -->
	<div class="z-10 flex flex-col items-center gap-6">
		<h1 class="hero-element font-['Sketch_Gothic_School',_cursive] text-6xl font-bold uppercase tracking-widest md:text-8xl lg:text-9xl opacity-0" style="font-family: 'Oswald', sans-serif; text-shadow: 2px 2px 0px rgba(0,0,0,0.1);">
			Cloud Cafe
		</h1>
		
		<p class="hero-element max-w-2xl font-['Playfair_Display'] text-xl italic tracking-wide text-gray-600 md:text-3xl opacity-0">
			Brewed to Perfection, Sipped With Joy
		</p>
        
        <!-- Smile icon decoration -->
        <div class="hero-element my-4 opacity-0">
             <svg width="60" height="30" viewBox="0 0 60 30" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round">
                <path d="M10 10 C 20 25, 40 25, 50 10" />
                <circle cx="15" cy="5" r="2" fill="currentColor" />
                <circle cx="45" cy="5" r="2" fill="currentColor" />
             </svg>
        </div>

		<button 
			onclick={scrollToMenu}
			class="hero-element group mt-8 flex items-center gap-2 bg-[#2c2c2c] px-8 py-4 text-sm font-bold uppercase tracking-widest text-[#FDFBF7] transition-all hover:bg-black hover:px-10 opacity-0"
		>
			Discover More Below
			<ArrowDown class="h-4 w-4 transition-transform group-hover:translate-y-1" />
		</button>
	</div>
</section>
