<script lang="ts">
	import Header from "$lib/Header.svelte";
 import "../app.css";
 let { children } = $props();
 import Animation from "$lib/Animation.svelte";
</script>
 
<Header />

{@render children?.()}

<Animation />
