# SpriteAI API Reference

This document provides a comprehensive API reference for the SpriteAI library. It includes detailed documentation for all public functions, their parameters, return values, and usage examples.

## Table of Contents

1. [generateCharacterSpritesheet](#generatecharacterspritesheet)
2. [generateLandscapeSprite](#generatelandscapesprite)
3. [Utility Functions](#utility-functions)

## generateCharacterSpritesheet

Generates a character spritesheet based on the provided parameters.

### Syntax

```javascript
generateCharacterSpritesheet(options)
```

### Parameters

`options` (Object): An object containing the following properties:

- `character` (String): Description of the character's appearance and style.
- `dimensions` (Object): Contains `width` and `height` of each sprite frame in pixels.
- `frames` (Number): Number of frames in the spritesheet.
- `style` (String, optional): Art style for the spritesheet (e.g., "pixel", "cartoon", "realistic").

### Return Value

Promise<Buffer>: A promise that resolves to a Buffer containing the generated spritesheet image data.

### Example

```javascript
const SpriteAI = require('spriteAI');

const options = {
  character: "A cute blue robot with glowing eyes",
  dimensions: { width: 64, height: 64 },
  frames: 8,
  style: "pixel"
};

SpriteAI.generateCharacterSpritesheet(options)
  .then(spritesheet => {
    // Save or process the spritesheet
  })
  .catch(error => {
    console.error("Error generating spritesheet:", error);
  });
```

## generateLandscapeSprite

Generates a landscape sprite based on the provided parameters.

### Syntax

```javascript
generateLandscapeSprite(options)
```

### Parameters

`options` (Object): An object containing the following properties:

- `description` (String): Detailed description of the landscape to generate.
- `dimensions` (Object): Contains `width` and `height` of the sprite in pixels.
- `style` (String, optional): Art style for the sprite (e.g., "pixel", "painterly", "low-poly").

### Return Value

Promise<Buffer>: A promise that resolves to a Buffer containing the generated landscape sprite image data.

### Example

```javascript
const SpriteAI = require('spriteAI');

const options = {
  description: "A serene forest glade with a small waterfall and colorful flowers",
  dimensions: { width: 256, height: 128 },
  style: "pixel"
};

SpriteAI.generateLandscapeSprite(options)
  .then(sprite => {
    // Save or process the landscape sprite
  })
  .catch(error => {
    console.error("Error generating landscape sprite:", error);
  });
```

## Utility Functions

### resizeSprite

Resizes a sprite or spritesheet to the specified dimensions.

#### Syntax

```javascript
resizeSprite(imageBuffer, newWidth, newHeight)
```

#### Parameters

- `imageBuffer` (Buffer): The original sprite image data.
- `newWidth` (Number): The desired width of the resized sprite.
- `newHeight` (Number): The desired height of the resized sprite.

#### Return Value

Promise<Buffer>: A promise that resolves to a Buffer containing the resized sprite image data.

#### Example

```javascript
const SpriteAI = require('spriteAI');

SpriteAI.generateCharacterSpritesheet(/* ... */)
  .then(spritesheet => {
    return SpriteAI.resizeSprite(spritesheet, 128, 128);
  })
  .then(resizedSpritesheet => {
    // Save or process the resized spritesheet
  })
  .catch(error => {
    console.error("Error resizing sprite:", error);
  });
```

### extractFrame

Extracts a single frame from a spritesheet.

#### Syntax

```javascript
extractFrame(spritesheetBuffer, frameIndex, frameDimensions)
```

#### Parameters

- `spritesheetBuffer` (Buffer): The spritesheet image data.
- `frameIndex` (Number): The index of the frame to extract (0-based).
- `frameDimensions` (Object): Contains `width` and `height` of each frame in pixels.

#### Return Value

Promise<Buffer>: A promise that resolves to a Buffer containing the extracted frame image data.

#### Example

```javascript
const SpriteAI = require('spriteAI');

SpriteAI.generateCharacterSpritesheet(/* ... */)
  .then(spritesheet => {
    return SpriteAI.extractFrame(spritesheet, 2, { width: 64, height: 64 });
  })
  .then(frame => {
    // Save or process the extracted frame
  })
  .catch(error => {
    console.error("Error extracting frame:", error);
  });
```

This API reference provides a comprehensive overview of the SpriteAI library's main functions and utilities. For more detailed information or advanced usage, please refer to the specific function documentation or reach out to our support team.