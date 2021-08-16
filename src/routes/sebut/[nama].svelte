<svelte:head>
	<title>Sebut nama</title>
</svelte:head>

<script context='module'>
	export async function load({page}){
		return {
			props: {
				nama: await page.params.nama
			}
		}
	}
</script>

<script>
	import {page} from '$app/stores'

	export let nama
	
	let acak
	$: if ($page.params.nama) {
		acak = Math.random()
	}
</script>

<p>{nama}</p>

<p>Panggil <a href="/sebut/{acak}">{acak}</a></p>