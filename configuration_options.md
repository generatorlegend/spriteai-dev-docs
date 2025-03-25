# Configuration Options for SpriteAI

This guide explains all the configuration options available in SpriteAI, detailing how to customize sprite generation, including options for size, style, animation states, and output formats. We'll provide examples of common configurations and explain how each option affects the generated sprites.

## Table of Contents

1. [Basic Configuration](#basic-configuration)
2. [Sprite Size](#sprite-size)
3. [Sprite Style](#sprite-style)
4. [Animation States](#animation-states)
5. [Output Formats](#output-formats)
6. [Advanced Options](#advanced-options)
7. [Common Configurations](#common-configurations)

## Basic Configuration

To start using SpriteAI, you need to create a configuration object. Here's a basic example:

```javascript
const config = {
  size: { width: 32, height: 32 },
  style: 'pixel',
  animationStates: ['idle', 'walk', 'jump'],
  outputFormat: 'png'
};

const sprite = new SpriteAI(config);
```

## Sprite Size

The `size` option determines the dimensions of your sprite. You can specify both width and height:

```javascript
size: { width: 64, height: 64 }
```

- `width`: The width of the sprite in pixels (default: 32)
- `height`: The height of the sprite in pixels (default: 32)

## Sprite Style

The `style` option sets the visual style of your sprite. Available options include:

- `'pixel'`: Classic pixel art style (default)
- `'cartoon'`: Smooth, cartoonish style
- `'realistic'`: More detailed, realistic style

Example:
```javascript
style: 'cartoon'
```

## Animation States

The `animationStates` option is an array of strings representing different animation states for your sprite. Common states include:

- `'idle'`: The sprite's resting state
- `'walk'`: Walking animation
- `'run'`: Running animation
- `'jump'`: Jumping animation
- `'attack'`: Attack animation

Example:
```javascript
animationStates: ['idle', 'walk', 'run', 'jump', 'attack']
```

## Output Formats

The `outputFormat` option specifies the file format for the generated sprites. Supported formats include:

- `'png'`: PNG format (default)
- `'jpeg'`: JPEG format
- `'gif'`: Animated GIF (for sprites with multiple animation states)
- `'spritesheet'`: A single image containing all animation frames

Example:
```javascript
outputFormat: 'spritesheet'
```

## Advanced Options

### Color Palette

You can specify a custom color palette for your sprites:

```javascript
colorPalette: ['#FF0000', '#00FF00', '#0000FF', '#FFFF00']
```

### Frame Count

For animated sprites, you can set the number of frames for each animation state:

```javascript
frameCounts: {
  idle: 4,
  walk: 8,
  run: 6,
  jump: 4,
  attack: 6
}
```

### Background

You can set a background color or make it transparent:

```javascript
background: 'transparent' // or '#RRGGBB' for a specific color
```

## Common Configurations

### Pixel Art Character

```javascript
const pixelCharacterConfig = {
  size: { width: 32, height: 32 },
  style: 'pixel',
  animationStates: ['idle', 'walk', 'jump'],
  outputFormat: 'spritesheet',
  colorPalette: ['#000000', '#FFFFFF', '#FF0000', '#00FF00', '#0000FF'],
  frameCounts: {
    idle: 2,
    walk: 4,
    jump: 2
  },
  background: 'transparent'
};
```

### Cartoon-style Item

```javascript
const cartoonItemConfig = {
  size: { width: 64, height: 64 },
  style: 'cartoon',
  animationStates: ['static', 'sparkle'],
  outputFormat: 'gif',
  colorPalette: ['#FFD700', '#FFA500', '#FFFFFF'],
  frameCounts: {
    static: 1,
    sparkle: 6
  },
  background: '#E6E6FA'
};
```

By adjusting these configuration options, you can create a wide variety of sprites tailored to your specific needs. Experiment with different combinations to achieve the desired look and feel for your game or application.