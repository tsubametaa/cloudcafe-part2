<script lang="ts">
	import MainMenu from './MainMenu.svelte';
	import Background from '$lib/components/ui/background.svelte';
	import cloudLogo from '$lib/assets/img/cloudcafe.svg';
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous">
	<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;500;700&family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&family=Roboto:wght@300;400;500&display=swap" rel="stylesheet">
</svelte:head>

<div class="relative min-h-screen bg-[var(--bg)] font-sans text-[#2c2c2c] overflow-hidden">
	<Background />
	
	<div class="relative z-10 mx-auto max-w-7xl px-8 py-32">
		<!-- Header -->
		<header id="menu" class="mb-20 flex flex-col items-center justify-center text-center scroll-mt-48">
			<div class="flex items-center gap-8 border-b-2 border-dashed border-[#2c2c2c] pb-6 px-20">
				<div class="hidden md:block text-right">
					<p class="text-xs uppercase tracking-widest">We are</p>
					<p class="font-serif text-2xl italic">Open</p>
					<p class="text-[10px] uppercase">Everyday</p>
					<p class="text-[10px]">8:00 am - 10:00 pm</p>
				</div>
				
				<h1 class="font-['Oswald'] text-7xl font-bold uppercase tracking-tighter">Menu</h1>
				
				<div class="hidden md:block text-left">
					<p class="text-xs uppercase tracking-widest">Make a</p>
					<p class="font-serif text-2xl italic">Reservation</p>
					<p class="text-[10px]">+62 8123 555</p>
					<p class="text-[10px]">@cloudcafe</p>
				</div>
			</div>
		</header>

		<!-- Main Menu Content -->
		<MainMenu />

		<!-- Footer / Logo -->
		<div class="mt-20 flex justify-end">
			<div class="text-right">
				<div class="flex items-center gap-2 justify-end">
                    <!-- Cloud Icon SVG -->
                    <img src={cloudLogo} alt="Cloud Cafe Logo" class="w-[100px] h-auto" />
				</div>
			</div>
		</div>
	</div>
</div>
