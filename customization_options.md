# Customization Options in SpriteAI

SpriteAI offers a wide range of customization options to tailor your generated sprites to your specific needs. This guide will walk you through the various parameters you can modify to achieve the desired results.

## Animation States

SpriteAI allows you to define multiple animation states for your sprites. These states can include:

- Idle
- Walk
- Run
- Jump
- Attack

To customize animation states, use the `setAnimationStates` function:

```javascript
spriteAI.setAnimationStates(['idle', 'walk', 'jump']);
```

This will generate sprites with the specified animation states. You can add or remove states as needed for your project.

## Art Styles

SpriteAI supports various art styles to match your game's aesthetic. Some available styles include:

- Pixel Art
- Hand-drawn
- Vector
- Realistic

To set the art style, use the `setArtStyle` function:

```javascript
spriteAI.setArtStyle('pixel');
```

Experiment with different styles to find the one that best suits your game's visual theme.

## Sprite Sizes

You can customize the size of your generated sprites to fit your game's resolution and design. Use the `setSpriteSize` function to specify the dimensions:

```javascript
spriteAI.setSpriteSize(32, 32); // Width: 32px, Height: 32px
```

Adjust the size parameters to match your game's requirements. Keep in mind that larger sizes may require more processing time.

## Background Removal

SpriteAI offers background removal options to generate sprites with transparent backgrounds. This feature is particularly useful for integrating sprites into various game environments.

To enable background removal, use the `setBackgroundRemoval` function:

```javascript
spriteAI.setBackgroundRemoval(true);
```

You can also specify a color tolerance to fine-tune the background removal process:

```javascript
spriteAI.setBackgroundRemoval(true, { colorTolerance: 10 });
```

## Examples

Here are some examples of how these customizations can affect your generated sprites:

1. Pixel Art Character with Multiple Animation States:

```javascript
spriteAI.setArtStyle('pixel');
spriteAI.setAnimationStates(['idle', 'walk', 'jump']);
spriteAI.setSpriteSize(16, 16);
spriteAI.setBackgroundRemoval(true);

const character = spriteAI.generateSprite('character');
```

This will create a 16x16 pixel art character with idle, walk, and jump animations, and a transparent background.

2. Hand-drawn Large Boss Character:

```javascript
spriteAI.setArtStyle('hand-drawn');
spriteAI.setAnimationStates(['idle', 'attack']);
spriteAI.setSpriteSize(128, 128);
spriteAI.setBackgroundRemoval(false);

const bossCharacter = spriteAI.generateSprite('boss');
```

This will generate a 128x128 hand-drawn boss character with idle and attack animations, including the background.

By combining these customization options, you can create a wide variety of sprites to suit your game's needs. Experiment with different combinations to achieve the perfect look for your project.