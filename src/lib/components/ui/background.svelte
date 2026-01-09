<script lang="ts">
	import {
		Coffee,
		Pizza,
		UtensilsCrossed,
		CupSoda,
		CakeSlice,
		Croissant,
		Sandwich,
		Drumstick,
		IceCream,
		Beer,
		Donut,
		Soup,
		Martini,
		Candy,
		Cookie,
		GlassWater,
		Popcorn,
		Wheat
	} from '@lucide/svelte';

	// Available icons for the doodle pattern
	const icons = [
		Coffee,
		Pizza,
		UtensilsCrossed,
		CupSoda,
		CakeSlice,
		Croissant,
		Sandwich,
		Drumstick,
		IceCream,
		Beer,
		Donut,
		Soup,
		Martini,
		Candy,
		Cookie,
		GlassWater,
		Popcorn,
		Wheat
	];

	// Generate a deterministic but random-looking set of positions
	// to avoid hydration mismatches, we'll generate this on mount or use a fixed seed logic.
	// For simplicity in Svelte, we can just define a fixed grid with variations.
    // We create a grid of cells and place an icon randomly within each cell.
    
    // Grid configuration
    const rows = 6;
    const cols = 6; 
    
    // Generate grid items
    let items: Array<{
        icon: any;
        top: number; // percentage
        left: number; // percentage
        rotation: number; // degrees
        scale: number;
    }> = [];

    // Simple pseudo-random function for consistent refreshing
    const seed = 12345;
    let currentSeed = seed;
    const random = () => {
        const x = Math.sin(currentSeed++) * 10000;
        return x - Math.floor(x);
    };

    for (let r = 0; r < rows; r++) {
        for (let c = 0; c < cols; c++) {
            // Pick a random icon
            const iconIndex = Math.floor(random() * icons.length);
            
            // Calculate base position (cell center)
            const baseTop = (r / rows) * 100;
            const baseLeft = (c / cols) * 100;
            
            // Add random offset within the cell (e.g., +/- 5%)
            const offsetTop = (random() - 0.5) * 10; 
            const offsetLeft = (random() - 0.5) * 10;

            // Random rotation (-30 to 30 degrees)
            const rotation = (random() - 0.5) * 60;
            
            // Random scale (0.8 to 1.2)
            const scale = 0.8 + random() * 0.4;

            items.push({
                icon: icons[iconIndex],
                top: Math.max(0, Math.min(100, baseTop + 8 + offsetTop)), // +8 to center in cell roughly
                left: Math.max(0, Math.min(100, baseLeft + 8 + offsetLeft)),
                rotation,
                scale
            });
        }
    }
</script>

<div class="fixed inset-0 z-0 overflow-hidden pointer-events-none select-none transition-opacity duration-1000">
    {#each items as item}
        <div 
            class="absolute text-[#2c2c2c] opacity-[0.07] transform transition-transform duration-700 ease-in-out hover:scale-110 hover:opacity-20"
            style="
                top: {item.top}%; 
                left: {item.left}%; 
                transform: translate(-50%, -50%) rotate({item.rotation}deg) scale({item.scale});
            "
        >
            <svelte:component this={item.icon} size={48} strokeWidth={1.5} />
        </div>
    {/each}
</div>
