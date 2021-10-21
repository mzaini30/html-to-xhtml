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

<textarea bind:value={input} placeholder="Tulis kodenya di sini"></textarea>
<textarea bind:value={output} readonly></textarea>