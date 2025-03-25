# Troubleshooting Guide

This guide covers common issues that users might encounter when using SpriteAI, along with solutions and workarounds. It includes problems related to sprite generation, image processing, and API usage.

## Table of Contents

1. [Sprite Generation Issues](#sprite-generation-issues)
2. [Image Processing Problems](#image-processing-problems)
3. [API Usage Errors](#api-usage-errors)
4. [Error Message Interpretation](#error-message-interpretation)

## Sprite Generation Issues

### Issue: Sprite generation fails or produces unexpected results

**Possible causes:**
- Incorrect input image format
- Insufficient image quality or resolution
- Incompatible AI model version

**Solutions:**
1. Ensure your input image is in a supported format (e.g., PNG, JPEG).
2. Use high-quality images with clear outlines and sufficient resolution.
3. Check if you're using the latest version of SpriteAI. Update if necessary:

```bash
npm update spriteai
```

4. If the issue persists, try adjusting the sprite generation parameters:

```javascript
const sprite = await SpriteAI.generateSprite(image, {
  quality: 'high',
  style: 'pixelart',
  resolution: 128
});
```

## Image Processing Problems

### Issue: Background removal not working correctly

**Possible causes:**
- Complex image backgrounds
- Poor contrast between subject and background
- Incorrect API usage

**Solutions:**
1. Use images with simple, contrasting backgrounds for better results.
2. Adjust the background removal threshold:

```javascript
const processedImage = await SpriteAI.removeBackground(image, {
  threshold: 0.8 // Increase for more aggressive background removal
});
```

3. Ensure you're calling the `removeBackground` function correctly:

```javascript
const SpriteAI = require('spriteai');

async function processImage(imagePath) {
  const image = await SpriteAI.loadImage(imagePath);
  const processedImage = await SpriteAI.removeBackground(image);
  // Further processing...
}
```

## API Usage Errors

### Issue: "Module not found" error

**Possible causes:**
- SpriteAI not installed properly
- Incorrect import statement

**Solutions:**
1. Reinstall SpriteAI:

```bash
npm uninstall spriteai
npm install spriteai
```

2. Ensure you're using the correct import statement:

```javascript
const SpriteAI = require('spriteai');
// or
import SpriteAI from 'spriteai';
```

### Issue: "Invalid API key" error

**Possible causes:**
- API key not set or invalid
- Environment variable not configured correctly

**Solutions:**
1. Double-check your API key in the SpriteAI dashboard.
2. Set the API key in your environment variables:

```bash
export SPRITEAI_API_KEY=your_api_key_here
```

3. Or set the API key programmatically:

```javascript
SpriteAI.setApiKey('your_api_key_here');
```

## Error Message Interpretation

Understanding error messages can help you quickly identify and resolve issues. Here are some common error messages and their meanings:

1. `Error: Invalid input image`: The provided image is not in a supported format or is corrupted. Try using a different image or converting it to a supported format.

2. `Error: API rate limit exceeded`: You've reached your API usage limit. Check your current plan and consider upgrading if necessary.

3. `Error: Insufficient memory`: The image processing task requires more memory than available. Try using a smaller image or increasing the memory allocation for your application.

4. `Error: Unsupported operation`: The requested operation is not supported by the current version of SpriteAI. Check the documentation for supported features and update your library if needed.

If you encounter an error message not listed here, please refer to the [API Reference](api-reference.md) for more detailed information on specific function calls and their potential errors.

For persistent issues or errors not covered in this guide, please contact our support team or open an issue on our GitHub repository.