<svelte:head>
	<title>Get</title>
</svelte:head>

<script context='module'>
	export async function load({fetch}){
		const res = await fetch('https://zen.echlus.my.id/')
		return {
			props: {
				data: await res.text()
			}
		}
	}
</script>

<script>
	export let data
</script>

{data}