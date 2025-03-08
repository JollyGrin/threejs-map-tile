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

<T.PerspectiveCamera makeDefault position={[0, 10, 40]} fov={40}>
	<OrbitControls autoRotate autoRotateSpeed={0.3} maxPolarAngle={(Math.PI / 2) * 0.9} />
</T.PerspectiveCamera>

<!-- Main sunlight - warm directional light -->
<T.DirectionalLight
	position={[5, 15, 10]}
	intensity={1.2}
	color="#ffd700"
	castShadow
	shadow.mapSize.width={2048}
	shadow.mapSize.height={2048}
	shadow.camera.far={50}
	shadow.camera.near={0.1}
/>

<!-- Ambient light for overall scene brightness -->
<T.AmbientLight intensity={0.1} color="#ffffff" castShadow />

<!-- Hemisphere light for sky/ground interaction -->
<T.HemisphereLight skyColor="#87ceeb" groundColor="#8b4513" intensity={0.2} />

<!-- Ground plane to receive shadows -->
<T.Mesh position={[0, -0.1, 0]} rotation.x={-Math.PI / 2} receiveShadow>
	<T.PlaneGeometry args={[200, 200]} />
	<T.MeshStandardMaterial color="#e6e6e6" roughness={1} metalness={0} />
</T.Mesh>

<Munich />
