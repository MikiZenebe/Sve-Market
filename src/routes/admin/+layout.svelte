<script lang="ts">
	import * as Sidebar from '$lib/components/ui/sidebar/index.js';
	import { User, LayoutDashboard, Box, Truck, Home, Blocks } from '@lucide/svelte';

	let { children } = $props();

	// Menu items.
	const items = [
		{
			title: 'Overview',
			url: 'overview',
			icon: LayoutDashboard
		},
		{
			title: 'Products',
			url: 'products',
			icon: Box
		},
		{
			title: 'Users',
			url: 'users',
			icon: User
		},
		{
			title: 'Orders',
			url: 'orders',
			icon: Truck
		},
		{
			title: 'Categories',
			url: 'categories',
			icon: Blocks
		},
		{
			title: 'Store front',
			url: '../',
			icon: Home
		}
	];
</script>

<Sidebar.Provider>
	<Sidebar.Root>
		<Sidebar.Content>
			<Sidebar.Group>
				<Sidebar.GroupLabel>Admin Dashboard</Sidebar.GroupLabel>
				<Sidebar.GroupContent>
					<Sidebar.Menu>
						{#each items as item (item.title)}
							<Sidebar.MenuItem>
								<Sidebar.MenuButton
									class=" from-[#ffa181] to-[#f8551f]  transition-all duration-300 ease-in-out hover:bg-gradient-to-l hover:text-white hover:shadow-lg hover:transition-all"
								>
									{#snippet child({ props })}
										<a href={`/admin/${item.url}`} {...props}>
											<item.icon />
											<span>{item.title}</span>
										</a>
									{/snippet}
								</Sidebar.MenuButton>
							</Sidebar.MenuItem>
						{/each}
					</Sidebar.Menu>
				</Sidebar.GroupContent>
			</Sidebar.Group>
		</Sidebar.Content>
	</Sidebar.Root>

	<main class="relative flex-1">
		{@render children?.()}
		<div class="absolute bottom-6 left-1/2 -translate-x-1/2">
			<Sidebar.Trigger
				class="cursor-pointer rounded-full bg-gradient-to-r from-[#ffa181] to-[#f8551f] p-4 text-white shadow-lg 
                   transition-all duration-300 ease-in-out
                   hover:scale-110 hover:from-[#f8551f] hover:to-[#ffa181] hover:shadow-2xl 
                   active:scale-95"
			/>
		</div>
	</main>
</Sidebar.Provider>
