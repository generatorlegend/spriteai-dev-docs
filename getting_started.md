---
id: getting-started
title: Getting Started with SpriteAI
sidebar_label: Getting Started
---

# Getting Started with SpriteAI

Welcome to SpriteAI! This guide will help you quickly set up and start using SpriteAI to generate character spritesheets and landscape sprites for your game development projects.

## Installation

To get started with SpriteAI, follow these steps:

1. Ensure you have Node.js version 18.0 or higher installed on your system.

2. Create a new directory for your project and navigate to it:

```bash
mkdir my-spriteai-project
cd my-spriteai-project
```

3. Initialize a new Node.js project:

```bash
npm init -y
```

4. Install SpriteAI:

```bash
npm install spriteai
```

## Basic Usage

Once you have SpriteAI installed, you can start using it to generate character spritesheets and landscape sprites.

### Generating Character Spritesheets

To generate a character spritesheet, use the `generateCharacterSpritesheet` function:

```javascript
const { generateCharacterSpritesheet } = require('spriteai');

async function createCharacter() {
  try {
    const spritesheet = await generateCharacterSpritesheet({
      style: 'pixel-art',
      character: 'warrior',
      actions: ['idle', 'walk', 'attack'],
      size: 64
    });
    
    console.log('Character spritesheet generated:', spritesheet);
  } catch (error) {
    console.error('Error generating character spritesheet:', error);
  }
}

createCharacter();
```

This example generates a pixel-art style warrior character spritesheet with idle, walk, and attack animations, each sprite being 64x64 pixels.

### Generating Landscape Sprites

To generate a landscape sprite, use the `generateLandscapeSprite` function:

```javascript
const { generateLandscapeSprite } = require('spriteai');

async function createLandscape() {
  try {
    const landscape = await generateLandscapeSprite({
      type: 'forest',
      time: 'day',
      weather: 'sunny',
      size: 256
    });
    
    console.log('Landscape sprite generated:', landscape);
  } catch (error) {
    console.error('Error generating landscape sprite:', error);
  }
}

createLandscape();
```

This example generates a 256x256 pixel forest landscape sprite with a daytime, sunny setting.

## Main Features

SpriteAI offers a range of features to enhance your sprite generation workflow:

1. **Character Spritesheet Generation**: Create full spritesheets for game characters with various actions and animations.
2. **Landscape Sprite Creation**: Generate diverse landscape elements for your game backgrounds and environments.
3. **Customizable Styles**: Choose from different art styles, including pixel art, cartoon, and realistic.
4. **Flexible Output Sizes**: Specify the size of your sprites to fit your game's resolution requirements.
5. **Weather and Time of Day Options**: For landscape sprites, customize the appearance based on weather conditions and time of day.
6. **Batch Processing**: Generate multiple sprites or spritesheets in a single operation for efficiency.

## Next Steps

Now that you've got the basics, explore the following topics to make the most of SpriteAI:

- [Advanced Configuration Options](./advanced-configuration.md)
- [Customizing Sprite Styles](./customizing-styles.md)
- [Batch Processing and Automation](./batch-processing.md)
- [Integrating SpriteAI with Game Engines](./game-engine-integration.md)

Happy sprite generating!