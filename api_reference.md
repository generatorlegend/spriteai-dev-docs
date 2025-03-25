# SpriteAI API Reference

This API reference provides comprehensive documentation for the SpriteAI library, covering all public functions, their parameters, return values, and usage examples. The reference is organized into three main categories: character generation, landscape generation, and utility functions.

## Table of Contents

1. [Character Generation](#character-generation)
2. [Landscape Generation](#landscape-generation)
3. [Utility Functions](#utility-functions)

## Character Generation

### generateCharacter(options)

Generates a character sprite based on the provided options.

**Parameters:**

- `options` (Object): Configuration options for character generation
  - `style` (String): The visual style of the character (e.g., "pixel", "cartoon", "realistic")
  - `gender` (String): The gender of the character ("male", "female", "neutral")
  - `race` (String): The race or species of the character (e.g., "human", "elf", "orc")
  - `class` (String): The character's class or profession (e.g., "warrior", "mage", "thief")
  - `equipment` (Array): List of equipment items to include in the sprite

**Returns:**

- (Buffer): A buffer containing the generated character sprite image

**Example:**

```javascript
const SpriteAI = require('spriteAI');

const characterOptions = {
  style: "pixel",
  gender: "female",
  race: "elf",
  class: "mage",
  equipment: ["staff", "robe", "hat"]
};

const characterSprite = await SpriteAI.generateCharacter(characterOptions);
```

### customizeCharacter(baseCharacter, customizations)

Customizes an existing character sprite with specific modifications.

**Parameters:**

- `baseCharacter` (Buffer): The original character sprite to be customized
- `customizations` (Object): Customization options
  - `hairColor` (String): New hair color (e.g., "blonde", "brown", "red")
  - `skinTone` (String): New skin tone (e.g., "light", "medium", "dark")
  - `outfit` (Object): Changes to the character's outfit
    - `top` (String): New top style
    - `bottom` (String): New bottom style
    - `accessories` (Array): List of accessories to add or remove

**Returns:**

- (Buffer): A buffer containing the customized character sprite image

**Example:**

```javascript
const SpriteAI = require('spriteAI');

const baseCharacter = await SpriteAI.generateCharacter(/* ... */);

const customizations = {
  hairColor: "red",
  skinTone: "medium",
  outfit: {
    top: "leather_armor",
    bottom: "cloth_pants",
    accessories: ["amulet", "bracers"]
  }
};

const customizedCharacter = await SpriteAI.customizeCharacter(baseCharacter, customizations);
```

## Landscape Generation

### generateLandscape(options)

Generates a landscape sprite based on the provided options.

**Parameters:**

- `options` (Object): Configuration options for landscape generation
  - `biome` (String): The type of environment (e.g., "forest", "desert", "tundra")
  - `time` (String): Time of day (e.g., "day", "night", "sunset")
  - `weather` (String): Weather conditions (e.g., "clear", "rainy", "snowy")
  - `size` (Object): Dimensions of the generated landscape
    - `width` (Number): Width of the landscape in pixels
    - `height` (Number): Height of the landscape in pixels

**Returns:**

- (Buffer): A buffer containing the generated landscape sprite image

**Example:**

```javascript
const SpriteAI = require('spriteAI');

const landscapeOptions = {
  biome: "forest",
  time: "sunset",
  weather: "clear",
  size: {
    width: 800,
    height: 600
  }
};

const landscapeSprite = await SpriteAI.generateLandscape(landscapeOptions);
```

### addLandscapeElements(baseLayer, elements)

Adds specific elements to an existing landscape sprite.

**Parameters:**

- `baseLayer` (Buffer): The original landscape sprite
- `elements` (Array): List of elements to add to the landscape
  - Each element is an object with properties:
    - `type` (String): Type of element (e.g., "tree", "rock", "building")
    - `position` (Object): Position of the element
      - `x` (Number): X-coordinate
      - `y` (Number): Y-coordinate
    - `size` (Object): Size of the element
      - `width` (Number): Width of the element
      - `height` (Number): Height of the element

**Returns:**

- (Buffer): A buffer containing the landscape sprite with added elements

**Example:**

```javascript
const SpriteAI = require('spriteAI');

const baseLandscape = await SpriteAI.generateLandscape(/* ... */);

const elements = [
  {
    type: "tree",
    position: { x: 100, y: 200 },
    size: { width: 50, height: 100 }
  },
  {
    type: "rock",
    position: { x: 300, y: 400 },
    size: { width: 30, height: 30 }
  }
];

const enhancedLandscape = await SpriteAI.addLandscapeElements(baseLandscape, elements);
```

## Utility Functions

### resizeSprite(sprite, newSize)

Resizes a sprite to the specified dimensions.

**Parameters:**

- `sprite` (Buffer): The original sprite image
- `newSize` (Object): New dimensions for the sprite
  - `width` (Number): New width in pixels
  - `height` (Number): New height in pixels

**Returns:**

- (Buffer): A buffer containing the resized sprite image

**Example:**

```javascript
const SpriteAI = require('spriteAI');

const originalSprite = await SpriteAI.generateCharacter(/* ... */);

const newSize = {
  width: 64,
  height: 64
};

const resizedSprite = await SpriteAI.resizeSprite(originalSprite, newSize);
```

### mergeLayers(layers)

Combines multiple sprite layers into a single image.

**Parameters:**

- `layers` (Array): An array of sprite buffers to be merged

**Returns:**

- (Buffer): A buffer containing the merged sprite image

**Example:**

```javascript
const SpriteAI = require('spriteAI');

const backgroundLayer = await SpriteAI.generateLandscape(/* ... */);
const characterLayer = await SpriteAI.generateCharacter(/* ... */);

const mergedScene = await SpriteAI.mergeLayers([backgroundLayer, characterLayer]);
```

### exportSprite(sprite, format)

Exports a sprite to a specific file format.

**Parameters:**

- `sprite` (Buffer): The sprite image to be exported
- `format` (String): The desired output format (e.g., "png", "jpg", "webp")

**Returns:**

- (Buffer): A buffer containing the sprite image in the specified format

**Example:**

```javascript
const SpriteAI = require('spriteAI');
const fs = require('fs');

const characterSprite = await SpriteAI.generateCharacter(/* ... */);

const pngSprite = await SpriteAI.exportSprite(characterSprite, "png");
fs.writeFileSync("character.png", pngSprite);
```

This concludes the API reference for the SpriteAI library. For more detailed information on specific use cases or advanced techniques, please refer to the other sections of our documentation.