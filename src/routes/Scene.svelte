<script lang="ts">
	import { T, useTask } from '@threlte/core';
	import { interactivity, OrbitControls } from '@threlte/extras';
	import { Spring } from 'svelte/motion';
	import Munich from './munich.svelte';

	interactivity();

	const scale = new Spring(1);

	let rotation = 0;
	useTask((delta) => {
		rotation += delta;
	});
</script>

<T.PerspectiveCamera
	makeDefault
	position={[20, 10, 10]}
	oncreate={(ref) => {
		ref.lookAt(-10, 0, -30);
	}}
>
	<OrbitControls autoRotate maxPolarAngle={(Math.PI / 2) * 0.9} />
</T.PerspectiveCamera>

<T.DirectionalLight position={[0, 10, 10]} castShadow />

<Munich />
