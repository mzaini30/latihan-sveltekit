<script context='module'>
	export async function load({page, fetch}){
		const angka = page.params.angka
		const ambilData = await fetch(`https://jsonplaceholder.typicode.com/posts/${angka}`)
		return {
			props: {
				data: await ambilData.json(),
				angka
			}
		}
	}
</script>

<script>
	export let data
	export let angka
</script>

<svelte:head>
	<title>Postingan ke-{angka}</title>
</svelte:head>

<p>{JSON.stringify(data)}</p>

<p>Menuju <a href="/postingan/{+angka + 1}">postingan ke-{+angka + 1}</a></p>