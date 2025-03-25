# Customization Options for SpriteAI

SpriteAI offers a wide range of customization options to tailor your generated sprites and landscapes to your specific needs. This guide will walk you through the various parameters and options available for both character spritesheets and landscape sprites.

## Character Spritesheet Customization

### Animation States

SpriteAI allows you to customize the animation states for your character sprites. You can specify which states you want to include in your spritesheet.

Example:
```javascript
const spriteAI = new SpriteAI();
const characterOptions = {
  animationStates: ['idle', 'walk', 'run', 'jump', 'attack']
};
const characterSprite = spriteAI.generateCharacter(characterOptions);
```

Available animation states include:
- idle
- walk
- run
- jump
- attack
- defend
- die

### Art Styles

You can adjust the art style of your character sprites to match your game's aesthetic.

Example:
```javascript
const characterOptions = {
  artStyle: 'pixel'
};
```

Available art styles:
- pixel
- cartoon
- realistic
- chibi

### Size and Resolution

Customize the size and resolution of your character sprites:

```javascript
const characterOptions = {
  size: {
    width: 64,
    height: 64
  },
  resolution: 'high'
};
```

Size options:
- width: number of pixels
- height: number of pixels

Resolution options:
- low
- medium
- high

### Color Palette

Specify a color palette for your character sprites:

```javascript
const characterOptions = {
  colorPalette: ['#FF0000', '#00FF00', '#0000FF']
};
```

## Landscape Sprite Customization

### Terrain Types

Choose from various terrain types for your landscape sprites:

```javascript
const landscapeOptions = {
  terrainType: 'forest'
};
const landscapeSprite = spriteAI.generateLandscape(landscapeOptions);
```

Available terrain types:
- forest
- desert
- mountain
- ocean
- grassland

### Time of Day

Adjust the lighting and mood of your landscape by specifying the time of day:

```javascript
const landscapeOptions = {
  timeOfDay: 'sunset'
};
```

Time of day options:
- dawn
- day
- sunset
- night

### Weather Effects

Add weather effects to your landscape sprites:

```javascript
const landscapeOptions = {
  weatherEffect: 'rain'
};
```

Weather effect options:
- clear
- cloudy
- rain
- snow
- fog

### Landscape Elements

Specify additional elements to include in your landscape:

```javascript
const landscapeOptions = {
  elements: ['trees', 'rocks', 'river']
};
```

Available landscape elements vary depending on the chosen terrain type.

## Advanced Customization

For more advanced customization options, you can use the `setCustomParameters` method:

```javascript
spriteAI.setCustomParameters({
  characterComplexity: 0.8,
  landscapeDetailLevel: 'high',
  animationSmoothness: 0.9
});
```

These advanced options allow for fine-tuning of the AI-generated sprites and may require experimentation to achieve desired results.

## Output Examples

Here are some examples of how different customization options affect the generated output:

1. Default character sprite:
   [Image placeholder for default character sprite]

2. Character sprite with 'cartoon' art style and custom color palette:
   [Image placeholder for customized character sprite]

3. Default landscape sprite (forest terrain):
   [Image placeholder for default landscape sprite]

4. Landscape sprite with 'night' time of day and 'rain' weather effect:
   [Image placeholder for customized landscape sprite]

By adjusting these customization options, you can create a wide variety of sprites that fit your game's unique style and requirements. Experiment with different combinations to find the perfect look for your project!