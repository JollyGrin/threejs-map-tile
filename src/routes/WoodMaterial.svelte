<!-- Custom Wood Shader Material -->
<script lang="ts">
    import { T } from '@threlte/core';

    const vertexShader = `
        varying vec2 vUv;
        varying vec3 vPosition;
        varying vec3 vNormal;

        void main() {
            vUv = uv;
            vPosition = position;
            vNormal = normal;
            gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
        }
    `;

    const fragmentShader = `
        varying vec2 vUv;
        varying vec3 vPosition;
        varying vec3 vNormal;
        
        uniform vec3 lightColor;
        uniform vec3 darkColor;
        uniform float time;
        
        // Noise functions
        float rand(vec2 n) { 
            return fract(sin(dot(n, vec2(12.9898, 4.1414))) * 43758.5453);
        }
        
        float noise(vec2 p) {
            vec2 ip = floor(p);
            vec2 u = fract(p);
            u = u*u*(3.0-2.0*u);
            
            float res = mix(
                mix(rand(ip), rand(ip+vec2(1.0,0.0)), u.x),
                mix(rand(ip+vec2(0.0,1.0)), rand(ip+vec2(1.0,1.0)), u.x), u.y);
            return res*res;
        }
        
        void main() {
            // Create wood grain pattern
            float frequency = 1.5;
            float noiseScale = 2.0;
            float ringScale = 4.0;
            
            vec2 pos = vPosition.xz * frequency;
            float pattern = noise(pos + vec2(time * 0.1));
            
            // Create rings
            float rings = fract(length(pos) * ringScale + pattern);
            rings = smoothstep(0.0, 0.7, rings);
            
            // Mix colors based on pattern
            vec3 color = mix(darkColor, lightColor, rings);
            
            // Add lighting based on normal
            float lighting = dot(vNormal, normalize(vec3(1.0, 1.0, 1.0)));
            color *= 0.5 + 0.5 * lighting;
            
            gl_FragColor = vec4(color, 1.0);
        }
    `;

    export let lightColor = [0.8, 0.6, 0.4]; // Light wood color
    export let darkColor = [0.4, 0.2, 0.1];  // Dark wood color
    export let time = 0;
</script>

<T.ShaderMaterial 
    {vertexShader}
    {fragmentShader}
    uniforms={{
        lightColor: { value: lightColor },
        darkColor: { value: darkColor },
        time: { value: time }
    }}
/>
