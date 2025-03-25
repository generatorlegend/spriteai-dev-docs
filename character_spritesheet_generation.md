# Character Spritesheet Generation

This guide provides a comprehensive overview of generating character spritesheets using the SpriteAI library. We'll focus on the `generateCharacterSpritesheet` function, its parameters, options, and return value. Additionally, we'll explore examples of different character types, animation states, and customization options to help you get the best results.

## Table of Contents

1. [Introduction](#introduction)
2. [The generateCharacterSpritesheet Function](#the-generatecharacterspritesheet-function)
3. [Parameters and Options](#parameters-and-options)
4. [Return Value](#return-value)
5. [Examples](#examples)
6. [Tips for Best Results](#tips-for-best-results)

## Introduction

The SpriteAI library provides powerful tools for generating character spritesheets programmatically. This can save significant time and effort in game development and animation projects. The `generateCharacterSpritesheet` function is the core of this functionality, allowing you to create diverse and customizable character sprites with various animation states.

## The generateCharacterSpritesheet Function

The `generateCharacterSpritesheet` function is the main entry point for creating character spritesheets. It takes a set of parameters that define the character's appearance, animations, and output options.

```javascript
const spritesheet = await generateCharacterSpritesheet(characterType, animationStates, options);
```

## Parameters and Options

### characterType (string)

Specifies the type of character to generate. Available options include:

- "human"
- "elf"
- "orc"
- "dwarf"
- "robot"

### animationStates (array)

An array of strings representing the animation states to include in the spritesheet. Common animation states include:

- "idle"
- "walk"
- "run"
- "jump"
- "attack"
- "defend"

### options (object)

An optional object containing additional configuration parameters:

- `width` (number): The width of each sprite frame in pixels (default: 64)
- `height` (number): The height of each sprite frame in pixels (default: 64)
- `format` (string): The output format of the spritesheet ("png" or "jpeg", default: "png")
- `quality` (number): The quality of the output image (0-100, default: 90)
- `backgroundColor` (string): The background color of the spritesheet (default: "transparent")
- `customizations` (object): Additional character customization options
  - `hairColor` (string): The color of the character's hair
  - `skinTone` (string): The skin tone of the character
  - `clothingColor` (string): The color of the character's clothing

## Return Value

The function returns a Promise that resolves to an object containing:

- `spritesheet` (Buffer): The generated spritesheet image data
- `metadata` (object): Information about the generated spritesheet
  - `frameCount` (number): The total number of frames in the spritesheet
  - `frameWidth` (number): The width of each frame
  - `frameHeight` (number): The height of each frame
  - `columns` (number): The number of columns in the spritesheet
  - `rows` (number): The number of rows in the spritesheet

## Examples

### Basic Human Character

```javascript
const humanSpritesheet = await generateCharacterSpritesheet("human", ["idle", "walk", "run"]);
```

### Customized Elf Character

```javascript
const elfSpritesheet = await generateCharacterSpritesheet("elf", ["idle", "attack", "defend"], {
  width: 128,
  height: 128,
  customizations: {
    hairColor: "#FFD700",
    skinTone: "#FFDAB9",
    clothingColor: "#228B22"
  }
});
```

### Robot Character with All Animation States

```javascript
const robotSpritesheet = await generateCharacterSpritesheet("robot", 
  ["idle", "walk", "run", "jump", "attack", "defend"], 
  { format: "jpeg", quality: 95 }
);
```

## Tips for Best Results

1. **Choose appropriate dimensions**: Select `width` and `height` values that provide enough detail for your character sprites without unnecessarily increasing file size.

2. **Limit animation states**: Include only the animation states you need to keep the spritesheet size manageable.

3. **Use customizations wisely**: Experiment with different customization options to create unique characters that fit your game's style.

4. **Consider performance**: If you're generating many spritesheets, you may want to implement caching or batch processing to improve performance.

5. **Test different formats**: Compare PNG and JPEG output to find the best balance between image quality and file size for your project.

6. **Implement error handling**: Wrap the `generateCharacterSpritesheet` function call in a try-catch block to handle any potential errors gracefully.

By following these guidelines and exploring the various options available in the `generateCharacterSpritesheet` function, you can create diverse and high-quality character spritesheets for your games and animations using the SpriteAI library.