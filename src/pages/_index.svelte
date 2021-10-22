<script>
	let input
	let output

	const browser = !import.meta.env.SSR

	$: if (input){
		if (browser) {
			let olah = new DOMParser().parseFromString(input, 'text/html')
			olah = new XMLSerializer().serializeToString(olah)
			output = olah
		}
	}
</script>

<textarea bind:value={input} placeholder="Write your code here"></textarea>
<textarea bind:value={output} class="readonly" readonly></textarea>
