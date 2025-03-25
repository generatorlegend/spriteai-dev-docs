# Character Spritesheet Generation

This guide explains how to generate character spritesheets using SpriteAI. We'll cover the `generateCharacterSpritesheet` function, its parameters, options, and how to customize the output. Examples of different character types and animation states are also included.

## Table of Contents

1. [Introduction](#introduction)
2. [The generateCharacterSpritesheet Function](#the-generatecharacterspritesheet-function)
3. [Parameters](#parameters)
4. [Options](#options)
5. [Customizing Output](#customizing-output)
6. [Examples](#examples)
   - [Basic Character](#basic-character)
   - [Fantasy Character](#fantasy-character)
   - [Sci-Fi Character](#sci-fi-character)
7. [Animation States](#animation-states)
8. [Best Practices](#best-practices)

## Introduction

SpriteAI is a powerful tool for generating character spritesheets programmatically. This guide will help you understand how to use the `generateCharacterSpritesheet` function to create diverse and customizable character sprites for your game or application.

## The generateCharacterSpritesheet Function

The `generateCharacterSpritesheet` function is the core of SpriteAI's character generation capabilities. It allows you to create a complete spritesheet with various animation states for a single character.

```javascript
const SpriteAI = require('spriteAI');

async function createCharacter() {
  const spritesheet = await SpriteAI.generateCharacterSpritesheet(options);
  // Use the generated spritesheet
}
```

## Parameters

The `generateCharacterSpritesheet` function takes a single `options` object as its parameter. This object contains all the necessary configuration for your character spritesheet.

## Options

Here are the key options you can specify:

- `characterType`: String - The type of character (e.g., 'human', 'elf', 'robot')
- `style`: String - The visual style (e.g., 'pixel', 'cartoon', 'realistic')
- `size`: Object - The dimensions of each sprite frame (e.g., { width: 64, height: 64 })
- `animationStates`: Array - List of animation states to generate (e.g., ['idle', 'walk', 'run', 'jump'])
- `palette`: Array - Color palette to use for the character
- `accessories`: Array - List of accessories to add to the character

## Customizing Output

You can customize the output of your character spritesheet by adjusting the options. Here are some ways to customize:

1. Change the `characterType` to create different kinds of characters.
2. Modify the `style` to alter the visual appearance.
3. Adjust the `size` for different sprite resolutions.
4. Add or remove `animationStates` to control which animations are generated.
5. Specify a custom `palette` to control the character's colors.
6. Add `accessories` to give your character unique items or features.

## Examples

### Basic Character

```javascript
const options = {
  characterType: 'human',
  style: 'pixel',
  size: { width: 32, height: 32 },
  animationStates: ['idle', 'walk'],
  palette: ['#FF0000', '#00FF00', '#0000FF'],
  accessories: ['hat']
};

const basicCharacter = await SpriteAI.generateCharacterSpritesheet(options);
```

### Fantasy Character

```javascript
const options = {
  characterType: 'elf',
  style: 'cartoon',
  size: { width: 64, height: 64 },
  animationStates: ['idle', 'walk', 'cast_spell'],
  palette: ['#8B4513', '#228B22', '#4682B4'],
  accessories: ['staff', 'cloak']
};

const fantasyCharacter = await SpriteAI.generateCharacterSpritesheet(options);
```

### Sci-Fi Character

```javascript
const options = {
  characterType: 'robot',
  style: 'realistic',
  size: { width: 128, height: 128 },
  animationStates: ['idle', 'walk', 'transform'],
  palette: ['#C0C0C0', '#FF4500', '#4B0082'],
  accessories: ['laser_gun', 'jetpack']
};

const sciFiCharacter = await SpriteAI.generateCharacterSpritesheet(options);
```

## Animation States

Animation states define the different actions or poses your character can perform. Common animation states include:

- `idle`: The character's resting pose
- `walk`: Walking animation
- `run`: Running animation
- `jump`: Jumping animation
- `attack`: Attack animation
- `crouch`: Crouching pose
- `climb`: Climbing animation

You can define custom animation states based on your game's needs.

## Best Practices

1. Start with a basic character and gradually add complexity.
2. Use consistent sizes and styles across related characters.
3. Test generated spritesheets in your game engine to ensure they work as expected.
4. Create a library of common options for quick character generation.
5. Experiment with different palettes and accessories to create unique characters.

By following this guide, you should now be able to generate a wide variety of character spritesheets using SpriteAI's `generateCharacterSpritesheet` function. Experiment with different options to create the perfect characters for your project!