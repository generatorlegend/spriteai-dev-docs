# SpriteAI Integration Guide

This guide provides instructions on integrating SpriteAI-generated spritesheets and landscape sprites into your game development projects. We'll cover how to incorporate these assets into popular game engines and frameworks, along with best practices for optimizing performance and managing your SpriteAI-generated assets.

## Table of Contents

1. [Introduction](#introduction)
2. [Importing SpriteAI Assets](#importing-spriteai-assets)
3. [Integration with Popular Game Engines](#integration-with-popular-game-engines)
   - [Unity](#unity)
   - [Unreal Engine](#unreal-engine)
   - [Godot](#godot)
4. [Using SpriteAI Assets in Your Game](#using-spriteai-assets-in-your-game)
5. [Best Practices](#best-practices)
6. [Troubleshooting](#troubleshooting)

## Introduction

SpriteAI generates high-quality spritesheets and landscape sprites that can be easily integrated into your game development workflow. This guide will help you incorporate these assets into your projects efficiently.

## Importing SpriteAI Assets

After generating your assets with SpriteAI, you'll typically receive them as image files (e.g., PNG) for spritesheets and individual sprite images for landscapes. To import these into your project:

1. Create an "Assets" or "Sprites" folder in your project directory.
2. Copy the SpriteAI-generated files into this folder.
3. Ensure your game engine or framework is set up to recognize and import these image files.

## Integration with Popular Game Engines

### Unity

To integrate SpriteAI assets in Unity:

1. In the Unity Editor, navigate to your "Assets" folder.
2. Right-click and select "Import New Asset" or drag and drop your SpriteAI files into the folder.
3. Select the imported spritesheet and set its Texture Type to "Sprite (2D and UI)".
4. If it's a spritesheet, set the Sprite Mode to "Multiple" and use the Sprite Editor to slice the spritesheet into individual sprites.

Example code for using a sprite in Unity:

```csharp
public class SpriteController : MonoBehaviour
{
    public Sprite spriteAISprite;
    
    void Start()
    {
        GetComponent<SpriteRenderer>().sprite = spriteAISprite;
    }
}
```

### Unreal Engine

For Unreal Engine:

1. In the Content Browser, right-click and select "Import to /Game/".
2. Navigate to your SpriteAI assets and import them.
3. Right-click on the imported texture and select "Create Paper2D Sprite".

Example Blueprint for using a sprite in Unreal Engine:

1. Drag a Paper Sprite component into your Blueprint.
2. In the Details panel, set the Source Sprite to your SpriteAI-generated sprite.

### Godot

To use SpriteAI assets in Godot:

1. In the FileSystem dock, right-click and select "Import".
2. Navigate to your SpriteAI assets and import them.
3. Drag the imported sprite into your scene.

Example GDScript for using a sprite in Godot:

```gdscript
extends Sprite

func _ready():
    texture = preload("res://path/to/spriteai_asset.png")
```

## Using SpriteAI Assets in Your Game

Once imported, you can use SpriteAI assets like any other sprite in your game. Here are some common use cases:

1. Character Sprites: Use spritesheets for character animations.
2. Environmental Elements: Implement landscape sprites as background elements or interactive objects.
3. UI Elements: Utilize individual sprites for buttons, icons, or other UI components.

## Best Practices

1. Asset Organization:
   - Keep your SpriteAI assets in a dedicated folder for easy management.
   - Use clear, descriptive names for your assets.

2. Performance Optimization:
   - Use texture atlases or spritesheets to reduce draw calls.
   - Implement sprite batching when possible.
   - Compress textures appropriately for your target platforms.

3. Version Control:
   - Include your SpriteAI assets in version control for easy collaboration and backup.

4. Asset Updates:
   - When updating sprites, maintain consistent file names to minimize code changes.
   - Consider using asset references instead of hard-coded paths for easier updates.

## Troubleshooting

If you encounter issues with your SpriteAI assets:

1. Ensure the image format is compatible with your game engine.
2. Check the import settings in your game engine to ensure proper configuration.
3. Verify that the sprite dimensions and pivot points are set correctly.
4. If animations are not working, check that your spritesheet is sliced correctly and the animation frames are in the right order.

For more specific issues or advanced integration techniques, please refer to the documentation of your chosen game engine or framework.