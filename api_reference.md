# SpriteAI API Reference

This document provides a comprehensive API reference for the SpriteAI library, detailing all public functions, their parameters, return values, and usage examples. SpriteAI is a powerful tool for generating character spritesheets and landscape sprites for game development projects.

## Table of Contents

1. [generateCharacterSpritesheet](#generatecharacterspritesheetconfig)
2. [generateLandscapeSprite](#generatelandscapespriteconfig)
3. [Utility Functions](#utility-functions)
   - [resizeSprite](#resizespriteimage-width-height)
   - [applyColorPalette](#applycolorpaletteimage-palette)

## generateCharacterSpritesheet(config)

Generates a character spritesheet based on the provided configuration.

### Parameters

`config` (Object): Configuration options for generating the character spritesheet.

- `style` (String): The visual style of the character (e.g., "pixel", "cartoon", "realistic").
- `gender` (String): The gender of the character ("male" or "female").
- `race` (String): The race or species of the character (e.g., "human", "elf", "orc").
- `class` (String): The character's class or profession (e.g., "warrior", "mage", "rogue").
- `animations` (Array): List of animations to include in the spritesheet (e.g., ["idle", "walk", "attack"]).
- `resolution` (Object): The resolution of each sprite frame.
  - `width` (Number): Width of each frame in pixels.
  - `height` (Number): Height of each frame in pixels.

### Returns

`Promise<Buffer>`: A promise that resolves with the generated spritesheet as a buffer.

### Example

```javascript
const SpriteAI = require('spriteai');

const config = {
  style: "pixel",
  gender: "female",
  race: "elf",
  class: "archer",
  animations: ["idle", "walk", "attack"],
  resolution: {
    width: 64,
    height: 64
  }
};

SpriteAI.generateCharacterSpritesheet(config)
  .then(spritesheet => {
    // Save or process the spritesheet
  })
  .catch(error => {
    console.error("Error generating spritesheet:", error);
  });
```

## generateLandscapeSprite(config)

Generates a landscape sprite based on the provided configuration.

### Parameters

`config` (Object): Configuration options for generating the landscape sprite.

- `type` (String): The type of landscape (e.g., "forest", "desert", "mountain").
- `time` (String): The time of day for the landscape (e.g., "day", "night", "sunset").
- `weather` (String): The weather condition (e.g., "clear", "rainy", "snowy").
- `style` (String): The visual style of the landscape (e.g., "pixel", "painted", "realistic").
- `resolution` (Object): The resolution of the sprite.
  - `width` (Number): Width of the sprite in pixels.
  - `height` (Number): Height of the sprite in pixels.

### Returns

`Promise<Buffer>`: A promise that resolves with the generated landscape sprite as a buffer.

### Example

```javascript
const SpriteAI = require('spriteai');

const config = {
  type: "forest",
  time: "sunset",
  weather: "clear",
  style: "pixel",
  resolution: {
    width: 256,
    height: 128
  }
};

SpriteAI.generateLandscapeSprite(config)
  .then(sprite => {
    // Save or process the landscape sprite
  })
  .catch(error => {
    console.error("Error generating landscape sprite:", error);
  });
```

## Utility Functions

### resizeSprite(image, width, height)

Resizes a sprite image to the specified dimensions.

#### Parameters

- `image` (Buffer): The input sprite image as a buffer.
- `width` (Number): The desired width of the resized sprite.
- `height` (Number): The desired height of the resized sprite.

#### Returns

`Promise<Buffer>`: A promise that resolves with the resized sprite as a buffer.

#### Example

```javascript
const SpriteAI = require('spriteai');

SpriteAI.resizeSprite(spriteBuffer, 128, 128)
  .then(resizedSprite => {
    // Use the resized sprite
  })
  .catch(error => {
    console.error("Error resizing sprite:", error);
  });
```

### applyColorPalette(image, palette)

Applies a specified color palette to a sprite image.

#### Parameters

- `image` (Buffer): The input sprite image as a buffer.
- `palette` (Array): An array of color values to apply to the image.

#### Returns

`Promise<Buffer>`: A promise that resolves with the color-adjusted sprite as a buffer.

#### Example

```javascript
const SpriteAI = require('spriteai');

const palette = ['#FF0000', '#00FF00', '#0000FF', '#FFFF00'];

SpriteAI.applyColorPalette(spriteBuffer, palette)
  .then(adjustedSprite => {
    // Use the color-adjusted sprite
  })
  .catch(error => {
    console.error("Error applying color palette:", error);
  });
```

This API reference provides a comprehensive overview of the SpriteAI library's main functions and utilities. By leveraging these functions, game developers can efficiently generate and manipulate character spritesheets and landscape sprites for their projects.