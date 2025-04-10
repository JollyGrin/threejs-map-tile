<script lang="ts">
	import { base } from '$app/paths';
	import { T, useTask } from '@threlte/core';
	import { useGltf } from '@threlte/extras';
	import { DRACOLoader } from 'three/examples/jsm/loaders/DRACOLoader.js';
	import WoodMaterial from './WoodMaterial.svelte';

	let {
		fallback,
		error,
		children,
		ref = $bindable(),
		...props
	}: {
		fallback?: any;
		error?: any;
		children?: any;
		ref?: any;
	} = $props();

	const dracoLoader = new DRACOLoader();
	dracoLoader.setDecoderPath(base + '/draco/');

	const gltf = useGltf(base + '/munich-transformed.glb', {
		dracoLoader: dracoLoader
	});

	// Animation time for wood shader
	let time = $state(0);
	useTask((delta) => {
		time += delta * 0.1; // Slow down the animation
	});
</script>

<T.Group bind:ref dispose={false} {...props} scale={0.1}>
	{#await gltf}
		{@render fallback?.()}
	{:then gltf}
		<T.Mesh geometry={gltf.nodes.map_2osm_buildings_1.geometry} castShadow>
			<WoodMaterial lightColor={[0.9, 0.7, 0.5]} darkColor={[0.4, 0.25, 0.15]} />
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_2.geometry}
				material={gltf.materials['43b3ae']}
				castShadow
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_3.geometry}
				material={gltf.materials.white}
				castShadow
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_4.geometry}
				material={gltf.materials.red}
				castShadow
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_5.geometry}
				material={gltf.materials.green}
				castShadow
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_6.geometry}
				material={gltf.materials.da7752}
			/>
			<T.Mesh geometry={gltf.nodes.map_2osm_buildings_7.geometry} material={gltf.materials.wall} />
			<T.Mesh geometry={gltf.nodes.map_2osm_buildings_8.geometry} material={gltf.materials.roof} />
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_9.geometry}
				material={gltf.materials.aaaaaa}
			/>
			<T.Mesh geometry={gltf.nodes.map_2osm_buildings_10.geometry} material={gltf.materials.grey} />
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_11.geometry}
				material={gltf.materials.e7d096}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_12.geometry}
				material={gltf.materials.yellow}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_13.geometry}
				material={gltf.materials.brown}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_14.geometry}
				material={gltf.materials['777777']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_15.geometry}
				material={gltf.materials.e96b39}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_16.geometry}
				material={gltf.materials.ffffe0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_17.geometry}
				material={gltf.materials.a0b0a0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_18.geometry}
				material={gltf.materials.eeeecc}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_19.geometry}
				material={gltf.materials.ac3232}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_20.geometry}
				material={gltf.materials.bab2a4}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_21.geometry}
				material={gltf.materials['5e5e5e']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_22.geometry}
				material={gltf.materials.lightcoral}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_23.geometry}
				material={gltf.materials.ffffd0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_24.geometry}
				material={gltf.materials.ffffc0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_25.geometry}
				material={gltf.materials.d0f0d0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_26.geometry}
				material={gltf.materials.eeeeee}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_27.geometry}
				material={gltf.materials.ffe0e0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_28.geometry}
				material={gltf.materials.b0e0e0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_29.geometry}
				material={gltf.materials.d96a4d}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_30.geometry}
				material={gltf.materials.lightgrey}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_31.geometry}
				material={gltf.materials.ffff90}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_32.geometry}
				material={gltf.materials.darkgray}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_33.geometry}
				material={gltf.materials.f3e5ab}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_34.geometry}
				material={gltf.materials.a07070}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_35.geometry}
				material={gltf.materials['90a090']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_36.geometry}
				material={gltf.materials.darkgray}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_37.geometry}
				material={gltf.materials.black}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_38.geometry}
				material={gltf.materials.c75d4d}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_39.geometry}
				material={gltf.materials['4a0505']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_40.geometry}
				material={gltf.materials['28282d']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_41.geometry}
				material={gltf.materials.a2a0a0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_42.geometry}
				material={gltf.materials.e05050}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_43.geometry}
				material={gltf.materials.dddddd}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_44.geometry}
				material={gltf.materials['908888']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_45.geometry}
				material={gltf.materials['493d26']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_46.geometry}
				material={gltf.materials.d05050}
			/>
			<T.Mesh geometry={gltf.nodes.map_2osm_buildings_47.geometry} material={gltf.materials.grey} />
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_48.geometry}
				material={gltf.materials.lightyellow}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_49.geometry}
				material={gltf.materials['6ebe9f']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_50.geometry}
				material={gltf.materials['666666']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_51.geometry}
				material={gltf.materials.bbbbbb}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_52.geometry}
				material={gltf.materials.ffffb0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_53.geometry}
				material={gltf.materials.c07070}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_54.geometry}
				material={gltf.materials['806050']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_55.geometry}
				material={gltf.materials['706058']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_56.geometry}
				material={gltf.materials.fff8c6}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_57.geometry}
				material={gltf.materials['90b090']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_58.geometry}
				material={gltf.materials['8fbc8f']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_59.geometry}
				material={gltf.materials.orange}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_60.geometry}
				material={gltf.materials.ffd0d0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_61.geometry}
				material={gltf.materials.ffefd5}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_62.geometry}
				material={gltf.materials.c0c0c0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_63.geometry}
				material={gltf.materials.a3331e}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_64.geometry}
				material={gltf.materials.white}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_65.geometry}
				material={gltf.materials.cc8c8e}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_66.geometry}
				material={gltf.materials['9097a4']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_67.geometry}
				material={gltf.materials.aeafaf}
			/>
			<T.Mesh geometry={gltf.nodes.map_2osm_buildings_68.geometry} material={gltf.materials.blue} />
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_69.geometry}
				material={gltf.materials.d0ffd0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_70.geometry}
				material={gltf.materials.e0e0e0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_71.geometry}
				material={gltf.materials.a05030}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_72.geometry}
				material={gltf.materials.e4b28b}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_73.geometry}
				material={gltf.materials.cc645c}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_74.geometry}
				material={gltf.materials.fff0e0}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_75.geometry}
				material={gltf.materials['808080']}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_76.geometry}
				material={gltf.materials.a09090}
			/>
			<T.Mesh geometry={gltf.nodes.map_2osm_buildings_77.geometry} material={gltf.materials.tan} />
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_78.geometry}
				material={gltf.materials.f0f090}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_79.geometry}
				material={gltf.materials.maroon}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_80.geometry}
				material={gltf.materials.e9967a}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_81.geometry}
				material={gltf.materials.lightgreen}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_82.geometry}
				material={gltf.materials.silver}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_83.geometry}
				material={gltf.materials.e2d5c5}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_84.geometry}
				material={gltf.materials.c7b8a1}
			/>
			<T.Mesh
				geometry={gltf.nodes.map_2osm_buildings_85.geometry}
				material={gltf.materials['888080']}
			/>
		</T.Mesh>
	{:catch err}
		{@render error?.({ error: err })}
	{/await}

	{@render children?.({ ref })}
</T.Group>
