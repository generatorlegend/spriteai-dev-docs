---
id: getting-started
title: Getting Started with SpriteAI
sidebar_label: Getting Started
---

# Getting Started with SpriteAI

Welcome to SpriteAI, a powerful library for generating character spritesheets using artificial intelligence. This guide will walk you through the process of installing SpriteAI, setting it up in your project, and creating your first AI-generated character spritesheet.

## Installation

To get started with SpriteAI, you'll need to install it in your project. SpriteAI can be installed using npm (Node Package Manager).

Open your terminal and run the following command:

```bash
npm install spriteai
```

## Basic Setup

Once you've installed SpriteAI, you can import it into your project. Create a new JavaScript file (e.g., `generate-sprite.js`) and add the following code:

```javascript
const SpriteAI = require('spriteai');

// Initialize SpriteAI
const spriteGenerator = new SpriteAI();
```

## Generating Your First Character Spritesheet

Now that you have SpriteAI set up, let's generate a simple character spritesheet. We'll create a basic character with a few animations.

```javascript
async function generateCharacterSpritesheet() {
  try {
    const character = await spriteGenerator.createCharacter({
      style: 'pixel-art',
      gender: 'female',
      hair: 'long',
      outfit: 'casual'
    });

    const animations = [
      'idle',
      'walk',
      'run',
      'jump'
    ];

    const spritesheet = await character.generateSpritesheet(animations);

    // Save the spritesheet
    await spritesheet.save('character-spritesheet.png');

    console.log('Character spritesheet generated successfully!');
  } catch (error) {
    console.error('Error generating character spritesheet:', error);
  }
}

generateCharacterSpritesheet();
```

This script does the following:

1. Creates a new character with specified attributes.
2. Defines a list of animations to include in the spritesheet.
3. Generates the spritesheet with the specified animations.
4. Saves the spritesheet as a PNG file.

To run this script, use the following command in your terminal:

```bash
node generate-sprite.js
```

## Key Concepts

### Character Creation

SpriteAI allows you to create characters by specifying various attributes such as style, gender, hair, and outfit. The AI uses these parameters to generate a unique character.

### Animations

You can define a list of animations for your character. SpriteAI will generate frames for each animation, creating a cohesive spritesheet that can be used in game development or other projects.

### Spritesheets

A spritesheet is a single image containing multiple frames of animation for a character. SpriteAI generates these spritesheets, which can be easily integrated into game engines or animation software.

## Integrating SpriteAI into Your Project

To use SpriteAI in a larger project:

1. Install SpriteAI as a dependency in your project.
2. Import SpriteAI in the files where you need to generate character sprites.
3. Use the SpriteAI API to create characters and generate spritesheets as needed.
4. Save the generated spritesheets and use them in your game or application.

## Next Steps

Now that you've created your first character spritesheet with SpriteAI, you can explore more advanced features:

- Customize character attributes in more detail
- Generate multiple characters and create party systems
- Implement real-time character customization in your applications
- Explore different animation styles and complexities

For more information on these advanced topics, please refer to our detailed API documentation and tutorials.

Happy sprite generating!