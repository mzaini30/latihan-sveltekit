<svelte:head>
	<title>Get biasa</title>
</svelte:head>

<script type="text/javascript">
	import {get} from 'axios'
	import {page} from '$app/stores'

	let datanya

	// hasilnya undefined pas awal
	async function ambil(){
		const {data} = await get('https://zen.thedev.id/')
		datanya = data
	}
	ambil()
</script>

<p>{datanya}</p>

<!-- yang $page udah bagian SSR -->
<p>{$page.path}</p>