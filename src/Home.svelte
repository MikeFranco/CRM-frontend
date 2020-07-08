<script>
	import Hero from './components/Hero.svelte';
	import Products from './components/DashProducts.svelte';
	import Delegaciones from './components/Dashdelegaciones.svelte';
	import Users from './components/Dashusers.svelte';
	import Tabs from './shared/Tabs.svelte';
	let items = ['Usuarios', 'Delegacion', 'Productos'];
	let activeitem = 'Usuarios';
	const tabChange = (e) => {
		activeitem = e.detail;
	} 

</script>
<Hero />
<main id="main">
<br>
<!--> <Tabs {activeitem} {items} on:tabChange={tabChange}  />
{#if activeitem === 'Usuarios' }
<Users />
{:else if activeitem === 'Delegacion'}
<Delegaciones />
{:else if activeitem === 'Productos'}
<Products />
{/if}
-->
</main>




<style>

	
</style>