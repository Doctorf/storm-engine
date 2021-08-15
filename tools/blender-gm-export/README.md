# Blender GM export

[Русская версия Readme](README_RUS.md)

## Export .gm Blender

If model has armature, it must be in pose position

![pose.img](readme-img/pose.png)

All meshes must be triangulated

Select root locator

![choose.img](readme-img/choose.png)

```
File -> Export... -> GM Export(.gm)
```

The game supports 65,535 vertices in one mesh.
It is possible that some vertices might be duplicated because of Blender data representation.
The optimal would be 40,000 - 50,000 vertices per mesh (might be more, it depends on the model)

Mesh can be split into multiple meshes if it has more vertices than supported.

The correct structure example (locators, meshes, textures, UV, shading) is presented on imported models

### Locators and meshes

All locators with children must have zero rotation

![rotation.img](readme-img/rotation.png)

If locator is parented to bone it must be parented this way

![locator-bone.img](readme-img/locator-bone.png)

If locator or mesh is parented to other locator it must be parented this way

![locator.img](readme-img/locator.png)

### Textures

Textures must be in .tga format

On animated models might be only one texture.
If you want multiple textures on the character, you need to add additional object
with a separate texture (e.g., characters with cuirass)

On models without animation might be one or two textures (main texture and texture with normals / decals - for e.g, ammo)

### Nodes structure

1) One texture


![single-texture.img](readme-img/single-texture.png)

2) Two textures

![two-textures.img](readme-img/two-textures.png)

## Issues

This is the first version of export and only one mesh per model is supported at the moment.
BSP currently is not supported.
Export of weapons and characters are supported.

## Blender Plugin Installation
```
Edit -> Preferences... -> Add-ons -> Install... -> Select export_gm.py from io_export_gm folder -> Enable "Export: SeaDogs GM"
```

## Blender Usage
```
File -> Export... -> GM Export(.gm)
```

## Author

[Artess999](https://github.com/Artess999)
