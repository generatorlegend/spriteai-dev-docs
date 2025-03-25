---
title: Getting Started with SpriteAI
sidebar_label: Getting Started
---

# Getting Started with SpriteAI

Welcome to SpriteAI, a powerful library for generating character spritesheets and landscape sprites using AI. This guide will walk you through the installation process and demonstrate basic usage examples to help you get started quickly.

## Installation

To install SpriteAI, you'll need Node.js version 18.0 or higher. You can install the library using npm:

```bash
npm install spriteai
```

## Basic Usage

### Importing SpriteAI

First, import the SpriteAI library in your JavaScript file:

```javascript
const SpriteAI = require('spriteai');
```

### Generating Character Spritesheets

To generate a character spritesheet, use the `generateCharacterSpritesheet` function:

```javascript
const SpriteAI = require('spriteai');

async function createCharacterSpritesheet() {
  try {
    const spritesheet = await SpriteAI.generateCharacterSpritesheet({
      character: 'warrior',
      style: 'pixel',
      size: 64,
      animations: ['idle', 'walk', 'attack']
    });
    
    console.log('Character spritesheet generated:', spritesheet);
    // Save or process the spritesheet as needed
  } catch (error) {
    console.error('Error generating character spritesheet:', error);
  }
}

createCharacterSpritesheet();
```

This example generates a pixel art warrior character spritesheet with idle, walk, and attack animations.

### Creating Landscape Sprites

To create landscape sprites, use the `generateLandscapeSprite` function:

```javascript
const SpriteAI = require('spriteai');

async function createLandscapeSprite() {
  try {
    const landscapeSprite = await SpriteAI.generateLandscapeSprite({
      type: 'forest',
      time: 'day',
      style: 'handdrawn',
      size: 256
    });
    
    console.log('Landscape sprite generated:', landscapeSprite);
    // Save or process the landscape sprite as needed
  } catch (error) {
    console.error('Error generating landscape sprite:', error);
  }
}

createLandscapeSprite();
```

This example generates a hand-drawn forest landscape sprite set during daytime.

## Main Functions Overview

### generateCharacterSpritesheet(options)

Generates a character spritesheet based on the provided options.

Options:
- `character` (string): Type of character (e.g., 'warrior', 'mage', 'archer')
- `style` (string): Art style (e.g., 'pixel', 'cartoon', 'realistic')
- `size` (number): Size of each sprite frame in pixels
- `animations` (array): List of animations to include

### generateLandscapeSprite(options)

Creates a landscape sprite based on the provided options.

Options:
- `type` (string): Type of landscape (e.g., 'forest', 'desert', 'mountains')
- `time` (string): Time of day (e.g., 'day', 'night', 'sunset')
- `style` (string): Art style (e.g., 'pixel', 'handdrawn', 'realistic')
- `size` (number): Size of the sprite in pixels

## Next Steps

Now that you've learned the basics of SpriteAI, you can:

1. Experiment with different options to create varied characters and landscapes.
2. Integrate the generated sprites into your game or application.
3. Explore advanced features and customization options in our API documentation.

For more detailed information on each function and additional features, please refer to our [API Reference](api-reference.md) documentation.

Happy sprite generating!