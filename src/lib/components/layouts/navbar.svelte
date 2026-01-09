<script lang="ts">
	import { onMount } from 'svelte';
	import { Menu, X } from '@lucide/svelte';
	import { fade, fly } from 'svelte/transition';
	import cloudLogo from '$lib/assets/img/cloudcafe.svg';

	let isScrolled = false;
	let isMobileMenuOpen = false;

	function handleScroll() {
		isScrolled = window.scrollY > 50;
	}

	function toggleMobileMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}

	onMount(() => {
		window.addEventListener('scroll', handleScroll);
		return () => {
			window.removeEventListener('scroll', handleScroll);
		};
	});
</script>

<nav
	class="fixed top-0 z-50 w-full transition-all duration-300 {isScrolled
		? 'bg-[#FDFBF7]/90 py-4 shadow-sm backdrop-blur-md'
		: 'bg-transparent py-6'}"
>
	<div class="mx-auto flex max-w-7xl items-center justify-between px-6 md:px-12">
		<!-- Logo -->
		<a href="/" class="group flex items-center gap-2">
			<img src={cloudLogo} alt="Cloud Cafe Logo" class="h-10 w-auto transition-transform group-hover:scale-110" />
		</a>

		<!-- Desktop Navigation -->
		<div class="hidden items-center gap-8 md:flex">
			{#each ['Home', 'Menu', 'Story', 'Contact'] as item}
				<a
					href="#{item.toLowerCase()}"
					class="font-['Oswald'] text-sm font-medium tracking-widest text-[#2c2c2c]/80 uppercase transition-colors hover:text-[#2c2c2c] hover:underline hover:decoration-2 hover:underline-offset-4"
				>
					{item}
				</a>
			{/each}
		</div>

		<!-- Actions -->
		<div class="hidden items-center gap-6 md:flex">
			<button
				class="rounded-none border-2 border-[#2c2c2c] bg-[#2c2c2c] px-6 py-2 font-['Oswald'] text-sm font-bold tracking-widest text-[#FDFBF7] uppercase transition-all hover:bg-transparent hover:text-black"
			>
				Book a Table
			</button>
		</div>

		<!-- Mobile Menu Toggle -->
		<button class="text-[#2c2c2c] md:hidden" onclick={toggleMobileMenu} aria-label="Toggle menu">
			{#if isMobileMenuOpen}
				<X size={28} />
			{:else}
				<Menu size={28} />
			{/if}
		</button>
	</div>

	<!-- Mobile Navigation Overlay -->
	{#if isMobileMenuOpen}
		<div
			transition:fade={{ duration: 200 }}
			class="absolute top-full left-0 h-screen w-full bg-[#FDFBF7] p-6 md:hidden"
		>
			<div class="flex flex-col items-center space-y-8 pt-12">
				{#each ['Home', 'Menu', 'Story', 'Contact'] as item}
					<a
						href="#{item.toLowerCase()}"
						class="font-['Oswald'] text-3xl font-bold tracking-widest text-[#2c2c2c] uppercase"
						onclick={toggleMobileMenu}
					>
						{item}
					</a>
				{/each}

				<div class="h-px w-24 bg-[#2c2c2c]/20"></div>

				<button
					class="w-full max-w-xs border-2 border-[#2c2c2c] bg-[#2c2c2c] px-8 py-3 font-['Oswald'] text-lg font-bold tracking-widest text-[#FDFBF7] uppercase"
				>
					Book a Table
				</button>
			</div>
		</div>
	{/if}
</nav>
