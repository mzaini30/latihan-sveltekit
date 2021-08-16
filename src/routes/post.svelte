<svelte:head>
	<title>Post</title>
</svelte:head>

<script context='module'>
	export async function load({fetch}){
		const res = await fetch('https://excalibur.mabaiz.web.id/sql.php', {
			method: 'post',
			headers: {
				'Content-Type': 'application/x-www-form-urlencoded'
			},
			body: 'id=d4a1b7365f4bd4b378112b4d1978883d&kunci=list'
		})
		return {
			props: {
				datanya: await res.json()
			}
		}
	}
</script>

<script>
	export let datanya
</script>

{JSON.stringify(datanya)}