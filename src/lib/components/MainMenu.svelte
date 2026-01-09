<script lang="ts">
	type MenuItem = {
		name: string;
		price: number;
		description: string;
	};

	let mainCourses: MenuItem[] = [
		{
			name: 'Chicken Sandwich',
			price: 43,
			description: 'Grilled chicken breast topped with crisp lettuce, juicy tomato, and creamy mayo, served in a fresh, toasted bun.'
		},
		{
			name: 'Tuna Sandwich',
			price: 46,
			description: 'Fresh tuna salad mixed with celery and mayo, paired with crisp lettuce and tomato slices, served on whole wheat bread.'
		},
		{
			name: 'Croissant',
			price: 32,
			description: 'A classic French pastry, light and flaky with a buttery taste, perfect for breakfast or a snack.'
		},
		{
			name: 'Hamburger',
			price: 26,
			description: 'A juicy beef patty with fresh lettuce, ripe tomato, melted cheese, and crunchy pickles, all in a soft, toasted bun.'
		},
		{
			name: 'Pizza',
			price: 56,
			description: 'Classic pizza featuring a crispy crust, tangy tomato sauce, and gooey melted cheese, with your choice of additional toppings.'
		},
		{
			name: 'Spaghetti Bolognese',
			price: 36,
			description: 'Spaghetti pasta topped with a rich and savory meat sauce made with ground beef, tomatoes, and Italian herbs.'
		},
		{
			name: 'Roasted Chicken',
			price: 37,
			description: 'Tender and juicy chicken roasted to perfection with a blend of herbs and spices, offering a flavorful and satisfying meal.'
		},
		{
			name: 'Fried Potatoes',
			price: 33,
			description: 'Crispy and golden fried potatoes, seasoned with salt and pepper, perfect as a side dish or a snack.'
		},
		{
			name: 'Spaghetti aglio e olio',
			price: 35,
			description: 'Simple yet flavorful spaghetti dish with garlic, olive oil, and red chili flakes, garnished with fresh parsley and grated Parmesan.'
		}
	];

	let desserts: MenuItem[] = [
		{
			name: 'Steamed buns',
			price: 23,
			description: 'Fluffy and moist steamed cake with a light sweetness, a delightful treat for any time.'
		},
		{
			name: 'Brownies',
			price: 19,
			description: 'Rich, fudgy chocolate brownie with a dense texture and intense chocolate flavor.'
		},
		{
			name: 'Cheesecake',
			price: 36,
			description: 'Creamy cheesecake with a smooth texture and a buttery graham cracker crust.'
		},
		{
			name: 'Muffin',
			price: 29,
			description: 'Soft and moist muffin available in flavors like blueberry and chocolate chip, perfect for breakfast or a snack.'
		},
		{
			name: 'Scones',
			price: 29,
			description: 'Buttery and crumbly English scones served with jam and clotted cream, great with tea or coffee.'
		},
		{
			name: 'Tiramisu',
			price: 45,
			description: 'Classic Italian dessert with layers of coffee-soaked ladyfingers, mascarpone cheese, and cocoa powder.'
		},
		{
			name: 'Ice Chocolate',
			price: 28,
			description: 'Creamy chocolate drink served cold with rich cocoa flavor, ideal for a refreshing treat.'
		},
		{
			name: 'Ice Vanilla',
			price: 28,
			description: 'Smooth and creamy vanilla-flavored iced drink, sweet and perfect for a hot day.'
		},
		{
			name: 'Ice Strawberry',
			price: 28,
			description: 'Fruity and refreshing iced drink with a sweet strawberry flavor, made with real strawberries.'
		}
	];

	let coffee: MenuItem[] = [
		{
			name: 'Espresso',
			price: 23,
			description: 'A bold and rich pure coffee shot, known for its intense flavor and aromatic essence, perfect for a quick caffeine boost.'
		},
		{
			name: 'Americano',
			price: 24,
			description: 'A strong and smooth coffee made by diluting a shot of espresso with hot water, offering a robust and clean coffee taste.'
		},
		{
			name: 'Cappuccino',
			price: 25,
			description: 'A balanced blend of espresso, steamed milk, and milk foam, delivering a harmonious combination of strong coffee and creamy texture.'
		},
		{
			name: 'Latte',
			price: 23,
			description: 'A smooth and creamy coffee drink made with espresso and a generous amount of steamed milk, topped with a light layer of foam.'
		},
		{
			name: 'Mocha',
			price: 22,
			description: 'A delightful fusion of espresso, rich chocolate, and steamed milk, creating a sweet and indulgent coffee experience with a chocolatey twist.'
		},
		{
			name: 'Macchiato',
			price: 26,
			description: 'A strong and flavorful espresso shot marked with a small amount of milk foam, providing a bold coffee taste with a hint of creaminess.'
		},
		{
			name: 'Cold Brew',
			price: 25,
			description: 'A smooth and refreshing coffee brewed slowly with cold water over several hours, resulting in a less acidic and naturally sweet coffee flavor.'
		}
	];

	let nonCoffee: MenuItem[] = [
		{
			name: 'Green Tea',
			price: 19,
			description: 'A light and refreshing tea with delicate, grassy notes, ideal for a calming and healthy beverage.'
		},
		{
			name: 'Earl Grey',
			price: 21,
			description: 'A popular black tea flavored with bergamot oil, offering a distinctive citrusy aroma and refreshing taste. Often enjoyed plain or with milk.'
		},
		{
			name: 'Milo Dino',
			price: 16,
			description: 'A chilled Malaysian drink with iced Milo topped with extra Milo powder, offering a rich, chocolatey taste that\'s both refreshing and indulgent.'
		},
		{
			name: 'Matcha Latte',
			price: 23,
			description: 'A light, refreshing tea with subtle grassy notes. Known for its health benefits and calming effects.'
		},
		{
			name: 'Thai Tea',
			price: 19,
			description: 'A sweet, creamy cold drink made with strong black tea, sugar, and condensed milk. Served over ice, it offers a perfect balance of rich flavor.'
		},
		{
			name: 'Lemonade',
			price: 18,
			description: 'A classic beverage made from fresh lemons, water, and a touch of sweetness. Perfectly balanced to quench your thirst on a hot day.'
		}
	];
</script>

<div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
	<!-- Food Section -->
	<div>
		<h2 class="mb-8 text-center font-['Oswald'] text-3xl font-bold uppercase tracking-wide">Food</h2>
		
		<div class="grid md:grid-cols-2 gap-x-8 gap-y-12">
			<!-- Main Course -->
			<div>
				<h3 class="mb-6 border-b border-black pb-2 text-center font-['Oswald'] text-xl font-bold uppercase">Main Course</h3>
				<div class="space-y-6">
					{#each mainCourses as item}
						<div class="group">
							<div class="flex justify-between items-baseline mb-1">
								<h4 class="font-bold text-lg group-hover:text-amber-700 transition-colors">{item.name}</h4>
								<span class="font-['Oswald'] font-bold text-lg">{item.price}</span>
							</div>
							<p class="text-sm text-gray-600 leading-snug">{item.description}</p>
						</div>
					{/each}
				</div>
			</div>

			<!-- Dessert -->
			<div>
				<h3 class="mb-6 border-b border-black pb-2 text-center font-['Oswald'] text-xl font-bold uppercase">Dessert</h3>
				<div class="space-y-6">
					{#each desserts as item}
						<div class="group">
							<div class="flex justify-between items-baseline mb-1">
								<h4 class="font-bold text-lg group-hover:text-amber-700 transition-colors">{item.name}</h4>
								<span class="font-['Oswald'] font-bold text-lg">{item.price}</span>
							</div>
							<p class="text-sm text-gray-600 leading-snug">{item.description}</p>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</div>

	<!-- Drinks Section -->
	<div>
		<h2 class="mb-8 text-center font-['Oswald'] text-3xl font-bold uppercase tracking-wide">Drinks</h2>
		
		<div class="grid md:grid-cols-2 gap-x-8 gap-y-12">
			<!-- Coffee -->
			<div>
				<h3 class="mb-6 border-b border-black pb-2 text-center font-['Oswald'] text-xl font-bold uppercase">Coffee</h3>
				<div class="space-y-6">
					{#each coffee as item}
						<div class="group">
							<div class="flex justify-between items-baseline mb-1">
								<h4 class="font-bold text-lg group-hover:text-amber-700 transition-colors">{item.name}</h4>
								<span class="font-['Oswald'] font-bold text-lg">{item.price}</span>
							</div>
							<p class="text-sm text-gray-600 leading-snug">{item.description}</p>
						</div>
					{/each}
				</div>
			</div>

			<!-- Non-Coffee -->
			<div>
				<h3 class="mb-6 border-b border-black pb-2 text-center font-['Oswald'] text-xl font-bold uppercase">Non - Coffee</h3>
				<div class="space-y-6">
					{#each nonCoffee as item}
						<div class="group">
							<div class="flex justify-between items-baseline mb-1">
								<h4 class="font-bold text-lg group-hover:text-amber-700 transition-colors">{item.name}</h4>
								<span class="font-['Oswald'] font-bold text-lg">{item.price}</span>
							</div>
							<p class="text-sm text-gray-600 leading-snug">{item.description}</p>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</div>
</div>
