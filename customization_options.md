# Customization Options in SpriteAI

This guide explores the various customization options available in the SpriteAI library. We'll cover how to modify parameters such as animation states, art styles, sprite sizes, and backgrounds to create unique and tailored sprite animations for your games.

## Table of Contents

1. [Introduction](#introduction)
2. [Animation States](#animation-states)
3. [Art Styles](#art-styles)
4. [Sprite Sizes](#sprite-sizes)
5. [Backgrounds](#backgrounds)
6. [Tips and Best Practices](#tips-and-best-practices)

## Introduction

SpriteAI offers a wide range of customization options to help you create the perfect sprites for your game. By adjusting various parameters, you can achieve specific visual effects and game styles that match your creative vision.

## Animation States

SpriteAI allows you to define and customize different animation states for your sprites. Common animation states include idle, walk, run, jump, and attack.

To customize animation states:

```javascript
const sprite = new SpriteAI.Sprite({
  animationStates: {
    idle: { frames: 4, loop: true },
    walk: { frames: 8, loop: true },
    jump: { frames: 6, loop: false }
  }
});
```

You can adjust the number of frames and whether the animation should loop for each state. Experiment with different frame counts to achieve smoother or more stylized animations.

## Art Styles

SpriteAI supports various art styles to match your game's aesthetic. You can choose from predefined styles or create custom ones.

To set an art style:

```javascript
sprite.setArtStyle('pixel');
```

Available art styles include:
- pixel
- cartoon
- realistic
- hand-drawn

For custom art styles, you can define your own style parameters:

```javascript
sprite.setCustomArtStyle({
  outlineThickness: 2,
  colorPalette: ['#FF0000', '#00FF00', '#0000FF'],
  shadingTechnique: 'cel'
});
```

## Sprite Sizes

Adjust the size of your sprites to fit your game's resolution and style:

```javascript
sprite.setSize(64, 64); // Width: 64px, Height: 64px
```

You can also set a scale factor to easily resize all your sprites:

```javascript
SpriteAI.setGlobalScale(1.5); // Increase all sprite sizes by 50%
```

## Backgrounds

SpriteAI allows you to generate or customize backgrounds for your sprites:

```javascript
sprite.setBackground({
  type: 'generated',
  style: 'forest',
  timeOfDay: 'sunset'
});
```

For custom backgrounds, you can provide your own image:

```javascript
sprite.setBackground({
  type: 'custom',
  image: 'path/to/background.png'
});
```

## Tips and Best Practices

1. **Consistency**: Maintain a consistent art style across all your sprites for a cohesive look.

2. **Performance**: Be mindful of sprite sizes and animation frame counts, especially for mobile games or websites.

3. **Reusability**: Create base sprites that can be easily customized for different characters or enemies.

4. **Experiment**: Don't be afraid to mix and match different customization options to create unique visual effects.

5. **Feedback**: Use the SpriteAI preview feature to quickly iterate on your designs and gather feedback from your team.

By leveraging these customization options, you can create distinctive and engaging sprites that bring your game world to life. Experiment with different combinations to find the perfect look for your project!