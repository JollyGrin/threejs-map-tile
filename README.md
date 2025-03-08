
# 3d-map-tile

## Pre-Reqs
- [blosm for blender](https://prochitecture.gumroad.com/l/blender-osm)
- blender

## load map
Install the plugin
`Edit > Settings > Addons > install from disk > select zip`

open the sidepane with `n`

select blosm, use openstreetmaps, select area, paste, and then import (screenshot in static/blosm-screen.png)

## export as glb

from blender export as glb

## import to gltf

Compress the gltf with threlte cli tools  https://threlte.xyz/docs/reference/gltf/getting-started#example
`npx @threlte/gltf@latest model.gltf --transform`

## copy the draco loader
ensure that the folder `static/draco/` has the appropriate files. Then use it in the gltf component

```ts
	const dracoLoader = new DRACOLoader();
	dracoLoader.setDecoderPath('/draco/');

	const gltf = useGltf('/munich-transformed.glb', {
		dracoLoader: dracoLoader
	});
```

---

# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.
