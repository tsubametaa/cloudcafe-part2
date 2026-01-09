<script lang="ts">
	import { onMount } from 'svelte';
	import { MapPin, Phone, Mail, Clock, Instagram, Facebook, Twitter } from '@lucide/svelte';
	import Background from '$lib/components/ui/background.svelte';

	let mounted = false;

	onMount(() => {
		mounted = true;
		setTimeout(() => {
			const elements = document.querySelectorAll('.contact-reveal');
			elements.forEach((el) => {
				(el as HTMLElement).style.opacity = '1';
				(el as HTMLElement).style.transform = 'translateY(0)';
			});
		}, 100);
	});

	const contactInfo = [
		{
			icon: Clock,
			title: 'We are Open',
			details: ['Everyday', '8:00 am - 10:00 pm']
		},
		{
			icon: Phone,
			title: 'Call Us',
			details: ['+62 8123 555']
		},
		{
			icon: Instagram,
			title: 'Follow Us',
			details: ['@cloudcafe']
		}
	];

	const socialLinks = [
		{ icon: Instagram, href: '#', label: 'Instagram' },
		{ icon: Facebook, href: '#', label: 'Facebook' },
		{ icon: Twitter, href: '#', label: 'Twitter' }
	];
</script>

<section id="contact" class="relative overflow-hidden py-32 bg-[var(--bg)] text-[#2c2c2c] scroll-mt-20">
	<Background />

	<div class="relative z-10 mx-auto max-w-7xl px-8">
		<!-- Header -->
		<div class="contact-reveal opacity-0 translate-y-5 transition-all duration-700 ease-out mb-16 text-center">
			<h2 class="font-['Oswald'] text-5xl font-bold uppercase leading-none tracking-tighter md:text-7xl">
				Get In Touch
			</h2>
			<p class="mt-4 text-lg text-gray-600 max-w-2xl mx-auto">
				We'd love to hear from you. Whether you have a question, want to book a table, or just want to say hello, 
				feel free to reach out.
			</p>
		</div>

		<div class="grid gap-12 lg:grid-cols-2 lg:gap-20">
			<!-- Contact Info Grid -->
			<div class="contact-reveal opacity-0 translate-y-5 transition-all duration-700 ease-out delay-100">
				<div class="grid gap-8 sm:grid-cols-2">
					{#each contactInfo as info}
						<div class="group flex gap-4">
							<div class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full border-2 border-[#2c2c2c] transition-all group-hover:bg-[#2c2c2c] group-hover:text-[var(--bg)]">
								<svelte:component this={info.icon} size={20} />
							</div>
							<div>
								<h3 class="font-['Oswald'] text-lg font-bold uppercase tracking-wide">{info.title}</h3>
								{#each info.details as detail}
									<p class="text-sm text-gray-600">{detail}</p>
								{/each}
							</div>
						</div>
					{/each}
				</div>

				<!-- Social Links -->
				<div class="mt-12 pt-8 border-t border-[#2c2c2c]/10">
					<h3 class="font-['Oswald'] text-lg font-bold uppercase tracking-wide mb-4">Follow Us</h3>
					<div class="flex gap-4">
						{#each socialLinks as social}
							<a 
								href={social.href} 
								aria-label={social.label}
								class="flex h-12 w-12 items-center justify-center rounded-full border-2 border-[#2c2c2c] transition-all hover:bg-[#2c2c2c] hover:text-[var(--bg)]"
							>
								<svelte:component this={social.icon} size={20} />
							</a>
						{/each}
					</div>
				</div>
			</div>

			<!-- Contact Form -->
			<div class="contact-reveal opacity-0 translate-y-5 transition-all duration-700 ease-out delay-200">
				<div class="rounded-2xl border-2 border-dashed border-[#2c2c2c] p-8">
					<h3 class="font-['Oswald'] text-2xl font-bold uppercase tracking-wide mb-6">Send a Message</h3>
					
					<form class="space-y-6">
						<div class="grid gap-6 sm:grid-cols-2">
							<div>
								<label for="name" class="block font-['Oswald'] text-sm font-bold uppercase tracking-wide mb-2">Name</label>
								<input 
									type="text" 
									id="name" 
									name="name"
									class="w-full border-2 border-[#2c2c2c]/20 bg-transparent px-4 py-3 text-sm transition-colors focus:border-[#2c2c2c] focus:outline-none"
									placeholder="Your name"
								/>
							</div>
							<div>
								<label for="email" class="block font-['Oswald'] text-sm font-bold uppercase tracking-wide mb-2">Email</label>
								<input 
									type="email" 
									id="email" 
									name="email"
									class="w-full border-2 border-[#2c2c2c]/20 bg-transparent px-4 py-3 text-sm transition-colors focus:border-[#2c2c2c] focus:outline-none"
									placeholder="Your email"
								/>
							</div>
						</div>
						
						<div>
							<label for="subject" class="block font-['Oswald'] text-sm font-bold uppercase tracking-wide mb-2">Subject</label>
							<input 
								type="text" 
								id="subject" 
								name="subject"
								class="w-full border-2 border-[#2c2c2c]/20 bg-transparent px-4 py-3 text-sm transition-colors focus:border-[#2c2c2c] focus:outline-none"
								placeholder="What's this about?"
							/>
						</div>
						
						<div>
							<label for="message" class="block font-['Oswald'] text-sm font-bold uppercase tracking-wide mb-2">Message</label>
							<textarea 
								id="message" 
								name="message"
								rows="5"
								class="w-full border-2 border-[#2c2c2c]/20 bg-transparent px-4 py-3 text-sm transition-colors focus:border-[#2c2c2c] focus:outline-none resize-none"
								placeholder="Your message..."
							></textarea>
						</div>
						
						<button 
							type="submit"
							class="w-full border-2 border-[#2c2c2c] bg-[#2c2c2c] px-8 py-4 font-['Oswald'] text-sm font-bold uppercase tracking-widest text-[var(--bg)] transition-all hover:bg-transparent hover:text-[#2c2c2c]"
						>
							Send Message
						</button>
					</form>
				</div>
			</div>
		</div>
	</div>
</section>
