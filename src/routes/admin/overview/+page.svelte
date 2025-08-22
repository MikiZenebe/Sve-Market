<script lang="ts">
	import * as Card from '$lib/components/ui/card';

	import { ArrowUpIcon, ShoppingCart } from '@lucide/svelte';
</script>

<div class="flex-1 space-y-4 p-8 pt-6">
	<h2 class="text-3xl font-bold capitalize tracking-tight">Dashboard</h2>
	<div class="grid gap-4 md:grid-cols-2 lg:grid-cols-3">
		<Card.Root class="shadow-none">
			<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
				<Card.Title class="text-sm font-medium">Total revenue</Card.Title>
				<ShoppingCart class="text-muted-foreground size-4" />
			</Card.Header>

			<Card.Content>
				<div class="text-2xl font-bold">$5000</div>
				<p class="text-muted-foreground text-xs">+50% from last month</p>
			</Card.Content>
		</Card.Root>

		<Card.Root class="shadow-none">
			<Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
				<Card.Title class="text-sm font-medium">New Customers</Card.Title>
				<ArrowUpIcon class="text-muted-foreground size-4" />
			</Card.Header>

			<Card.Content>
				<div class="text-2xl font-bold">+20</div>
				<p class="text-muted-foreground text-xs">+20% from last month</p>
			</Card.Content>
		</Card.Root>
	</div>
</div>
