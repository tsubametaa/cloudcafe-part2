<script lang="ts">
	import Navbar from '$lib/components/layouts/navbar.svelte';
	import Menu from '$lib/components/Menu.svelte';
	import HeroSection from '$lib/components/HeroSection.svelte';
	import Story from '$lib/components/Story.svelte';
	import ContactSection from '$lib/components/ContactSection.svelte';
	import Footer from '$lib/components/layouts/footer.svelte';

</script>

<Navbar />

<main>
	<HeroSection />
	<Menu />
	<Story />
	<ContactSection />
</main>

<Footer />
