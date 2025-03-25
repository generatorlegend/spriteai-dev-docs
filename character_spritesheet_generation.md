# Character Spritesheet Generation with SpriteAI

This guide explains how to generate character spritesheets using SpriteAI, focusing on the `generateCharacterSpritesheet` function, its parameters, options, and customization possibilities.

## Table of Contents

1. [Introduction](#introduction)
2. [The generateCharacterSpritesheet Function](#the-generatecharacterspritesheet-function)
3. [Parameters and Options](#parameters-and-options)
4. [Customizing Output](#customizing-output)
5. [Examples](#examples)
6. [Using Spritesheets in Game Development](#using-spritesheets-in-game-development)

## Introduction

SpriteAI is a powerful tool for generating character spritesheets programmatically. It allows game developers to create diverse character animations quickly and efficiently.

## The generateCharacterSpritesheet Function

The `generateCharacterSpritesheet` function is the core of SpriteAI's character generation capabilities. It creates a complete spritesheet based on the provided parameters and options.

```javascript
const SpriteAI = require('spriteAI');

const spritesheet = await SpriteAI.generateCharacterSpritesheet(characterType, options);
```

## Parameters and Options

### characterType (required)

A string specifying the type of character to generate. Common types include:

- 'human'
- 'orc'
- 'elf'
- 'dwarf'
- 'monster'

### options (optional)

An object containing various customization options:

```javascript
{
  animationStates: ['idle', 'walk', 'run', 'attack'],
  direction: ['front', 'back', 'left', 'right'],
  size: { width: 64, height: 64 },
  style: 'pixel',
  color: {
    skin: '#F5D0A9',
    hair: '#8B4513',
    outfit: '#4169E1'
  }
}
```

## Customizing Output

You can customize the output spritesheet by adjusting the options object. Some key customization areas include:

- Animation states
- Character directions
- Sprite size
- Art style
- Color palette

## Examples

### Basic Human Character

```javascript
const humanSpritesheet = await SpriteAI.generateCharacterSpritesheet('human', {
  animationStates: ['idle', 'walk'],
  direction: ['front', 'back'],
  size: { width: 32, height: 32 }
});
```

### Detailed Orc Warrior

```javascript
const orcWarrior = await SpriteAI.generateCharacterSpritesheet('orc', {
  animationStates: ['idle', 'walk', 'run', 'attack', 'defend'],
  direction: ['front', 'back', 'left', 'right'],
  size: { width: 128, height: 128 },
  style: 'detailed',
  color: {
    skin: '#355E3B',
    armor: '#8B4513',
    weapon: '#C0C0C0'
  }
});
```

## Using Spritesheets in Game Development

Once you have generated a spritesheet, you can use it in your game development process:

1. Save the spritesheet as an image file.
2. Load the spritesheet in your game engine.
3. Define animation frames based on the spritesheet layout.
4. Create animation sequences for each character state.

Example (using a hypothetical game engine):

```javascript
const game = new GameEngine();
const playerSprite = game.loadSpritesheet('player_spritesheet.png', 64, 64);

const idleAnimation = playerSprite.defineAnimation([0, 1, 2, 3], 0.1);
const walkAnimation = playerSprite.defineAnimation([4, 5, 6, 7], 0.08);

player.setAnimation('idle', idleAnimation);
player.setAnimation('walk', walkAnimation);
```

By leveraging SpriteAI's `generateCharacterSpritesheet` function, you can create diverse and customized character spritesheets for your game development projects efficiently.