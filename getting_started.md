```yaml
---
title: Getting Started with SpriteAI
description: A comprehensive guide to installing and using the SpriteAI library for generating character spritesheets and landscape sprites
sidebar_position: 1
---

# Getting Started with SpriteAI

Welcome to SpriteAI, a powerful library for generating character spritesheets and landscape sprites using artificial intelligence. This guide will walk you through the installation process, basic usage, and an overview of the main features.

## Installation

To get started with SpriteAI, you'll need to install it in your project. SpriteAI can be installed using npm (Node Package Manager).

1. Open your terminal or command prompt.
2. Navigate to your project directory.
3. Run the following command:

```bash
npm install spriteai
```

This will install SpriteAI and its dependencies in your project.

## Basic Usage

### Importing SpriteAI

To use SpriteAI in your project, you'll need to import it first. Add the following line at the top of your JavaScript file:

```javascript
const SpriteAI = require('spriteai');
```

### Generating Character Spritesheets

To generate a character spritesheet, use the `generateCharacterSpritesheet` function:

```javascript
const SpriteAI = require('spriteai');

async function createCharacter() {
  try {
    const characterOptions = {
      style: 'pixel',
      gender: 'female',
      hairColor: 'brown',
      outfitColor: 'red'
    };

    const spritesheet = await SpriteAI.generateCharacterSpritesheet(characterOptions);
    console.log('Character spritesheet generated:', spritesheet.url);
  } catch (error) {
    console.error('Error generating character spritesheet:', error);
  }
}

createCharacter();
```

This example generates a pixel art female character with brown hair and a red outfit.

### Generating Landscape Sprites

To create landscape sprites, use the `generateLandscapeSprite` function:

```javascript
const SpriteAI = require('spriteai');

async function createLandscape() {
  try {
    const landscapeOptions = {
      type: 'forest',
      time: 'day',
      season: 'summer',
      style: 'pixel'
    };

    const landscapeSprite = await SpriteAI.generateLandscapeSprite(landscapeOptions);
    console.log('Landscape sprite generated:', landscapeSprite.url);
  } catch (error) {
    console.error('Error generating landscape sprite:', error);
  }
}

createLandscape();
```

This example generates a pixel art forest landscape during a summer day.

## Main Features Overview

SpriteAI offers a range of features to help you create diverse and customizable sprites:

1. **Character Spritesheet Generation**: Create full character spritesheets with various poses and animations.
2. **Landscape Sprite Creation**: Generate background and environmental sprites for your games or applications.
3. **Customization Options**: Adjust parameters like style, colors, and specific attributes to fine-tune your sprites.
4. **Multiple Art Styles**: Choose from various styles including pixel art, cartoon, and realistic.
5. **Batch Processing**: Generate multiple sprites in a single API call for efficiency.
6. **Export Options**: Save your sprites in different formats and resolutions.

## Next Steps

Now that you've got the basics down, you can explore more advanced features and customization options in our API documentation. Happy sprite generating!

For more detailed information on each feature and advanced usage, please refer to our [API Reference](/api-reference) section.

If you encounter any issues or have questions, don't hesitate to check out our [Troubleshooting Guide](/troubleshooting) or [contact our support team](/support).