# Character Spritesheet Generation

This guide provides a comprehensive overview of generating character spritesheets using the SpriteAI library. We'll explore the `generateCharacterSpritesheet` function, its parameters, and various options to create customized character sprites for your game or application.

## Table of Contents

1. [Introduction](#introduction)
2. [The generateCharacterSpritesheet Function](#the-generatecharacterspritesheet-function)
3. [Parameters and Options](#parameters-and-options)
4. [Character Types](#character-types)
5. [Animation States](#animation-states)
6. [Customization Options](#customization-options)
7. [Best Practices and Tips](#best-practices-and-tips)
8. [Troubleshooting](#troubleshooting)

## Introduction

The SpriteAI library provides powerful tools for generating character spritesheets programmatically. This allows you to create a wide variety of character sprites with different appearances, animations, and styles, all through code.

## The generateCharacterSpritesheet Function

The main function for creating character spritesheets is `generateCharacterSpritesheet`. This function takes several parameters to customize the output spritesheet.

```javascript
const spritesheet = await SpriteAI.generateCharacterSpritesheet(characterType, options);
```

## Parameters and Options

The `generateCharacterSpritesheet` function accepts two main parameters:

1. `characterType` (string): Specifies the base type of character to generate.
2. `options` (object): An object containing various customization options.

### Options Object

```javascript
const options = {
  animationStates: ['idle', 'walk', 'run', 'jump'],
  style: 'pixel',
  resolution: 64,
  palette: ['#FF0000', '#00FF00', '#0000FF'],
  accessories: ['hat', 'glasses'],
  background: 'transparent'
};
```

## Character Types

SpriteAI supports various character types, including:

- humanoid
- animal
- monster
- robot

Example:

```javascript
const humanoidSprite = await SpriteAI.generateCharacterSpritesheet('humanoid', options);
const animalSprite = await SpriteAI.generateCharacterSpritesheet('animal', options);
```

## Animation States

You can specify which animation states to include in your spritesheet. Common states include:

- idle
- walk
- run
- jump
- attack
- defend

Example:

```javascript
const options = {
  animationStates: ['idle', 'walk', 'run', 'attack'],
  // ... other options
};

const characterSprite = await SpriteAI.generateCharacterSpritesheet('humanoid', options);
```

## Customization Options

### Style

Set the visual style of your character sprite:

```javascript
const options = {
  style: 'pixel', // Options: 'pixel', 'cartoon', 'realistic'
  // ... other options
};
```

### Resolution

Specify the resolution of each sprite frame:

```javascript
const options = {
  resolution: 64, // Size in pixels (e.g., 32, 64, 128)
  // ... other options
};
```

### Color Palette

Define a custom color palette for your character:

```javascript
const options = {
  palette: ['#FF0000', '#00FF00', '#0000FF', '#FFFF00'],
  // ... other options
};
```

### Accessories

Add accessories to your character:

```javascript
const options = {
  accessories: ['hat', 'glasses', 'sword'],
  // ... other options
};
```

## Best Practices and Tips

1. Start with a low resolution (e.g., 32x32) for prototyping and increase as needed.
2. Use a consistent color palette across all your game assets for a cohesive look.
3. Generate variations of the same character type to create diverse NPCs or enemies.
4. Combine different animation states to create more complex animations.

## Troubleshooting

If you encounter issues while generating spritesheets, try the following:

1. Ensure you're using the latest version of the SpriteAI library.
2. Check that all parameters and options are correctly formatted.
3. Verify that the specified character type and animation states are supported.
4. If generating large spritesheets, consider breaking them into smaller chunks to avoid memory issues.

For more advanced usage and additional features, refer to the SpriteAI API documentation.