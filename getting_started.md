---
title: Getting Started with SpriteAI
description: A step-by-step guide to help you start using SpriteAI for generating character spritesheets and landscape sprites.
sidebar_position: 1
---

# Getting Started with SpriteAI

Welcome to SpriteAI! This guide will walk you through the process of setting up and using SpriteAI to generate character spritesheets and landscape sprites for your projects. Let's get started!

## Installation

To begin using SpriteAI, you'll need to install it in your project. You can do this using npm (Node Package Manager):

```bash
npm install spriteai
```

## Basic Usage

Once you have SpriteAI installed, you can start using its main functions: `generateCharacterSpritesheet` and `generateLandscapeSprite`. Let's look at how to use each of these.

### Generating Character Spritesheets

To create a character spritesheet, use the `generateCharacterSpritesheet` function:

```javascript
import { generateCharacterSpritesheet } from 'spriteai';

const characterOptions = {
  style: 'pixel',
  gender: 'female',
  hair: 'long',
  outfit: 'adventurer'
};

generateCharacterSpritesheet(characterOptions)
  .then(spritesheet => {
    console.log('Character spritesheet generated:', spritesheet);
    // Use the spritesheet in your game or application
  })
  .catch(error => {
    console.error('Error generating character spritesheet:', error);
  });
```

The `characterOptions` object allows you to customize various aspects of your character's appearance. Adjust these options to create diverse characters for your project.

### Generating Landscape Sprites

To create a landscape sprite, use the `generateLandscapeSprite` function:

```javascript
import { generateLandscapeSprite } from 'spriteai';

const landscapeOptions = {
  type: 'forest',
  time: 'day',
  season: 'summer'
};

generateLandscapeSprite(landscapeOptions)
  .then(sprite => {
    console.log('Landscape sprite generated:', sprite);
    // Use the sprite in your game or application
  })
  .catch(error => {
    console.error('Error generating landscape sprite:', error);
  });
```

The `landscapeOptions` object allows you to specify the type of landscape and other environmental factors. Experiment with different combinations to create varied landscapes for your scenes.

## Integrating SpriteAI into Your Project

To integrate SpriteAI into your project, follow these steps:

1. Import the necessary functions from SpriteAI at the top of your file:

   ```javascript
   import { generateCharacterSpritesheet, generateLandscapeSprite } from 'spriteai';
   ```

2. Call the functions where needed in your code, passing in the appropriate options.

3. Handle the returned promises to access the generated spritesheets or sprites.

4. Implement error handling to manage any issues that may occur during sprite generation.

## Core Concepts

Understanding these core concepts will help you make the most of SpriteAI:

- **Spritesheets**: A collection of individual sprite images combined into a single image file. SpriteAI generates character spritesheets that include various poses and animations.

- **Sprites**: Individual images that represent characters, objects, or scenery in your game or application.

- **Generation Options**: Both `generateCharacterSpritesheet` and `generateLandscapeSprite` accept option objects that allow you to customize the output. Experiment with these options to create diverse and unique assets.

- **Asynchronous Generation**: Sprite generation is an asynchronous process. Always use `.then()` or `async/await` to handle the generated results.

## Example: Creating a Scene

Here's a simple example of how you might use SpriteAI to create a scene with a character and a landscape:

```javascript
import { generateCharacterSpritesheet, generateLandscapeSprite } from 'spriteai';

async function createScene() {
  try {
    const character = await generateCharacterSpritesheet({
      style: 'pixel',
      gender: 'male',
      hair: 'short',
      outfit: 'knight'
    });

    const landscape = await generateLandscapeSprite({
      type: 'castle',
      time: 'night',
      season: 'winter'
    });

    console.log('Scene assets generated:');
    console.log('Character:', character);
    console.log('Landscape:', landscape);

    // Use the generated assets to render your scene
    renderScene(character, landscape);
  } catch (error) {
    console.error('Error creating scene:', error);
  }
}

function renderScene(character, landscape) {
  // Your rendering logic here
  console.log('Rendering scene with generated assets...');
}

createScene();
```

This example demonstrates how to generate both a character and a landscape, and then use them together in a scene.

## Conclusion

You're now ready to start using SpriteAI in your projects! Remember to explore the API documentation for more detailed information on available options and advanced usage. Happy sprite generating!