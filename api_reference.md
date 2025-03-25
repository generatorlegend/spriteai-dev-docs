# API Reference

This document provides a comprehensive API reference for SpriteAI, detailing all public functions, their parameters, return values, and usage examples. The reference is organized by function category for easy navigation.

## Table of Contents

1. [Character Sprite Generation](#character-sprite-generation)
   - [generateCharacterSpritesheet](#generatecharacterspritesheet)
2. [Landscape Sprite Generation](#landscape-sprite-generation)
   - [generateLandscapeSprite](#generatelandscapesprite)
3. [Utility Functions](#utility-functions)

## Character Sprite Generation

### generateCharacterSpritesheet

Generates a character spritesheet based on the provided parameters.

#### Parameters

- `character` (object): An object containing character details
  - `name` (string): The name of the character
  - `style` (string): The visual style of the character (e.g., "pixel", "cartoon")
  - `attributes` (object): Additional attributes for character customization

#### Returns

- `Promise<Buffer>`: A promise that resolves to a Buffer containing the generated spritesheet image data

#### Usage Example

```javascript
const SpriteAI = require('spriteai');

const character = {
  name: "Hero",
  style: "pixel",
  attributes: {
    hair: "brown",
    eyes: "blue",
    outfit: "armor"
  }
};

SpriteAI.generateCharacterSpritesheet(character)
  .then(spritesheet => {
    // Use the spritesheet buffer
    console.log("Spritesheet generated successfully");
  })
  .catch(error => {
    console.error("Error generating spritesheet:", error);
  });
```

## Landscape Sprite Generation

### generateLandscapeSprite

Generates a landscape sprite based on the provided parameters.

#### Parameters

- `landscape` (object): An object containing landscape details
  - `type` (string): The type of landscape (e.g., "forest", "desert", "mountain")
  - `time` (string): The time of day (e.g., "day", "night", "sunset")
  - `weather` (string): The weather condition (e.g., "clear", "rainy", "snowy")

#### Returns

- `Promise<Buffer>`: A promise that resolves to a Buffer containing the generated landscape sprite image data

#### Usage Example

```javascript
const SpriteAI = require('spriteai');

const landscape = {
  type: "forest",
  time: "sunset",
  weather: "clear"
};

SpriteAI.generateLandscapeSprite(landscape)
  .then(sprite => {
    // Use the landscape sprite buffer
    console.log("Landscape sprite generated successfully");
  })
  .catch(error => {
    console.error("Error generating landscape sprite:", error);
  });
```

## Utility Functions

This section will be updated with utility functions as they become available in the SpriteAI library.