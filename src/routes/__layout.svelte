<script>
	import '../app.css';
	import NavBar from "$lib/NavBar.svelte";
</script>

<NavBar appName="ChartJs Basic"
		export let btnMenu = "Who am I"
		menu1="barCharts"
		menu1URL="/barCharts"
		menu2 = "Charts"
		menu2URL= "/charts"
/>
<slot />
