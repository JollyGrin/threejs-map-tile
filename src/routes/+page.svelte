<script lang="ts">
	import { Canvas } from '@threlte/core';
	import Scene from './Scene.svelte';
</script>

<div class=" fixed top-3 left-3 z-50 opacity-50">
	<a href="https://github.com/JollyGrin/threejs-map-tile ">git </a>
</div>

<div class="h-screen w-screen">
	<Canvas>
		<Scene />
	</Canvas>
</div>
