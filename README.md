# Godot Object Space Dissolve Shader

Dissolves the object with respect to the Object Space, even if the object is transformed in world/global space (moved around and rotated), the dissolve position and offset is preserved.

## Godot 3

Object space in the [shader](./Godot3/3D%20Vertical%20Dissolve%20Object%20Space.shader) is calculated with: 

```gdscript
vec3 position = (inverse(WORLD_MATRIX) * CAMERA_MATRIX * vec4(VERTEX, 1.0)).xyz;
```

./doc/dissolve-godot3.mp4

## Godot 4

Currently broken - I couldn't find a way to dissolve in object space, it's currently in view space (if the object or camera moves, the dissolve offset also moves).

Current try in the [shader](./Godot4/ObjectSpaceDissolve.gdshader) to calculate object space (bugged): 

```gdscript
vec3 position = (inverse(MODEL_MATRIX) * vec4(VERTEX, 1.0)).xyz;
```

./doc/dissolve-godot3.mp4