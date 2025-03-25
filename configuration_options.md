# Configuration Options for SpriteAI

This guide explains the configuration options available in SpriteAI for generating character spritesheets and landscape sprites. We'll focus on the options objects for `generateCharacterSpritesheet` and `generateLandscapeSprite` functions, detailing each option, its possible values, and how it affects the sprite generation process.

## Character Spritesheet Configuration

The `generateCharacterSpritesheet` function accepts an options object with the following properties:

### size
- Type: `number`
- Default: `64`
- Description: The size of each individual sprite in the spritesheet, in pixels.
- Example:
  ```javascript
  {
    size: 32
  }
  ```
  This will generate smaller sprites, suitable for lower resolution games.

### rows
- Type: `number`
- Default: `4`
- Description: The number of rows in the spritesheet.
- Example:
  ```javascript
  {
    rows: 6
  }
  ```
  This will create a spritesheet with more animation frames or character states.

### columns
- Type: `number`
- Default: `3`
- Description: The number of columns in the spritesheet.
- Example:
  ```javascript
  {
    columns: 4
  }
  ```
  This will allow for more character directions or variations.

### style
- Type: `string`
- Possible values: `'pixel'`, `'cartoon'`, `'realistic'`
- Default: `'pixel'`
- Description: The visual style of the generated sprites.
- Example:
  ```javascript
  {
    style: 'cartoon'
  }
  ```
  This will create sprites with a more cartoonish appearance.

### theme
- Type: `string`
- Possible values: `'fantasy'`, `'sci-fi'`, `'modern'`
- Default: `'fantasy'`
- Description: The thematic setting for the character sprites.
- Example:
  ```javascript
  {
    theme: 'sci-fi'
  }
  ```
  This will generate characters suitable for a science fiction game.

## Landscape Sprite Configuration

The `generateLandscapeSprite` function accepts an options object with the following properties:

### width
- Type: `number`
- Default: `256`
- Description: The width of the generated landscape sprite, in pixels.
- Example:
  ```javascript
  {
    width: 512
  }
  ```
  This will create a wider landscape sprite.

### height
- Type: `number`
- Default: `256`
- Description: The height of the generated landscape sprite, in pixels.
- Example:
  ```javascript
  {
    height: 128
  }
  ```
  This will create a shorter landscape sprite.

### biome
- Type: `string`
- Possible values: `'forest'`, `'desert'`, `'tundra'`, `'mountain'`
- Default: `'forest'`
- Description: The type of environment to generate.
- Example:
  ```javascript
  {
    biome: 'desert'
  }
  ```
  This will create a desert landscape with appropriate features.

### timeOfDay
- Type: `string`
- Possible values: `'day'`, `'night'`, `'sunset'`
- Default: `'day'`
- Description: The lighting condition for the landscape.
- Example:
  ```javascript
  {
    timeOfDay: 'sunset'
  }
  ```
  This will generate a landscape with sunset lighting and colors.

### detailLevel
- Type: `string`
- Possible values: `'low'`, `'medium'`, `'high'`
- Default: `'medium'`
- Description: The level of detail in the generated landscape.
- Example:
  ```javascript
  {
    detailLevel: 'high'
  }
  ```
  This will create a more detailed and complex landscape sprite.

## Examples

### Character Spritesheet Example

```javascript
const characterOptions = {
  size: 48,
  rows: 4,
  columns: 4,
  style: 'pixel',
  theme: 'fantasy'
};

const characterSpritesheet = await generateCharacterSpritesheet(characterOptions);
```

This configuration will generate a 48x48 pixel character spritesheet with 4 rows and 4 columns, in a pixelated fantasy style.

### Landscape Sprite Example

```javascript
const landscapeOptions = {
  width: 512,
  height: 256,
  biome: 'mountain',
  timeOfDay: 'sunset',
  detailLevel: 'high'
};

const landscapeSprite = await generateLandscapeSprite(landscapeOptions);
```

This configuration will create a 512x256 pixel mountain landscape sprite with a sunset lighting effect and high level of detail.

By adjusting these configuration options, you can create a wide variety of character spritesheets and landscape sprites to suit your game's needs. Experiment with different combinations to achieve the desired visual style and complexity for your project.