# SpriteAI API Reference

This document provides a comprehensive API reference for SpriteAI, detailing the main functions and utilities available for generating character spritesheets and landscape sprites.

## Table of Contents

1. [Main Functions](#main-functions)
   - [generateCharacterSpritesheet](#generatecharacterspritesheet)
   - [generateLandscapeSprite](#generatelandscapesprite)
2. [Utility Functions](#utility-functions)
   - [removeBackgroundColor](#removebackgroundcolor)
3. [SDK-specific Functions](#sdk-specific-functions)
   - [fetchAvailableAnimationStates](#fetchavailableanimationstates)

## Main Functions

### generateCharacterSpritesheet

Generates a character spritesheet based on the provided parameters and options.

#### Parameters

- `character` (object): An object containing character details.
  - `name` (string): The name of the character.
  - `description` (string): A brief description of the character's appearance and style.
- `options` (object, optional): Additional options for customizing the spritesheet generation.
  - `size` (number, default: 64): The size of each sprite in pixels.
  - `animationStates` (array of strings, optional): Specific animation states to include in the spritesheet.
  - `style` (string, optional): The artistic style to apply to the generated sprites.

#### Return Value

- `Promise<object>`: A promise that resolves to an object containing:
  - `spritesheet` (Buffer): The generated spritesheet image as a buffer.
  - `metadata` (object): Metadata about the generated spritesheet, including dimensions and included animation states.

#### Example Usage

```javascript
const SpriteAI = require('spriteai');

const character = {
  name: 'Adventurer',
  description: 'A brave warrior with long hair and shining armor'
};

const options = {
  size: 128,
  animationStates: ['idle', 'walk', 'attack'],
  style: 'pixel-art'
};

SpriteAI.generateCharacterSpritesheet(character, options)
  .then(result => {
    console.log('Spritesheet generated:', result.metadata);
    // Save or process the spritesheet buffer (result.spritesheet)
  })
  .catch(error => {
    console.error('Error generating spritesheet:', error);
  });
```

### generateLandscapeSprite

Generates a landscape sprite based on the provided description and options.

#### Parameters

- `description` (string): A detailed description of the desired landscape.
- `options` (object, optional): Additional options for customizing the sprite generation.
  - `size` (object, default: { width: 256, height: 256 }): The dimensions of the generated sprite.
  - `style` (string, optional): The artistic style to apply to the generated sprite.
  - `time` (string, optional): The time of day to depict in the landscape (e.g., 'day', 'night', 'sunset').

#### Return Value

- `Promise<object>`: A promise that resolves to an object containing:
  - `sprite` (Buffer): The generated landscape sprite image as a buffer.
  - `metadata` (object): Metadata about the generated sprite, including dimensions and applied options.

#### Example Usage

```javascript
const SpriteAI = require('spriteai');

const description = 'A serene mountain lake surrounded by pine trees, with snow-capped peaks in the background';

const options = {
  size: { width: 512, height: 256 },
  style: 'watercolor',
  time: 'sunset'
};

SpriteAI.generateLandscapeSprite(description, options)
  .then(result => {
    console.log('Landscape sprite generated:', result.metadata);
    // Save or process the sprite buffer (result.sprite)
  })
  .catch(error => {
    console.error('Error generating landscape sprite:', error);
  });
```

## Utility Functions

### removeBackgroundColor

Removes the background color from a sprite image, making it transparent.

#### Parameters

- `sprite` (Buffer): The input sprite image as a buffer.
- `backgroundColor` (string, optional): The color to be removed, in hexadecimal format (e.g., '#FFFFFF'). If not provided, the function will attempt to detect the background color automatically.

#### Return Value

- `Promise<Buffer>`: A promise that resolves to a buffer containing the processed sprite image with a transparent background.

#### Example Usage

```javascript
const SpriteAI = require('spriteai');

// Assuming you have a sprite buffer from a previous operation
const spriteBuffer = // ... sprite buffer ...

SpriteAI.removeBackgroundColor(spriteBuffer, '#00FF00')
  .then(processedSprite => {
    console.log('Background removed successfully');
    // Save or further process the sprite with transparent background
  })
  .catch(error => {
    console.error('Error removing background:', error);
  });
```

## SDK-specific Functions

### fetchAvailableAnimationStates

Retrieves the list of available animation states for character spritesheets.

#### Parameters

None

#### Return Value

- `Promise<Array<string>>`: A promise that resolves to an array of strings representing the available animation states.

#### Example Usage

```javascript
const SpriteAI = require('spriteai');

SpriteAI.fetchAvailableAnimationStates()
  .then(states => {
    console.log('Available animation states:', states);
    // Use the states to configure spritesheet generation
  })
  .catch(error => {
    console.error('Error fetching animation states:', error);
  });
```

This function is useful for dynamically populating the `animationStates` option in the `generateCharacterSpritesheet` function, ensuring that only supported states are requested.