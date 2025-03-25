# Troubleshooting Guide for SpriteAI

This guide addresses common issues users might encounter when using the SpriteAI library. It covers problems related to image generation, background removal, API interactions, and file handling. Follow the step-by-step solutions and explanations for each issue.

## Table of Contents

1. [Image Generation Issues](#image-generation-issues)
2. [Background Removal Problems](#background-removal-problems)
3. [API Interaction Errors](#api-interaction-errors)
4. [File Handling Difficulties](#file-handling-difficulties)

## Image Generation Issues

### Problem: Low-quality or distorted images

**Symptoms**: Generated images appear blurry, pixelated, or have unexpected artifacts.

**Solution**:

1. Check the input parameters:
   - Ensure the `width` and `height` parameters are set to appropriate values.
   - Verify that the `prompt` is clear and descriptive.

2. Adjust the `num_inference_steps`:
   - Increase the number of steps for higher quality (e.g., from 50 to 100).
   - Example:
     ```javascript
     const result = await spriteAI.generateImage({
       prompt: "A cute cartoon robot",
       width: 512,
       height: 512,
       num_inference_steps: 100
     });
     ```

3. Try different seeds:
   - Use the `seed` parameter to generate variations.
   - Example:
     ```javascript
     const result = await spriteAI.generateImage({
       prompt: "A cute cartoon robot",
       seed: 42
     });
     ```

4. Update the SpriteAI library:
   - Ensure you're using the latest version of the library.
   - Run `npm update spriteai` to update.

## Background Removal Problems

### Problem: Inaccurate background removal

**Symptoms**: The background is not fully removed, or parts of the subject are removed along with the background.

**Solution**:

1. Improve input image quality:
   - Use high-resolution images with clear contrast between subject and background.
   - Ensure proper lighting in the original image.

2. Adjust the `threshold` parameter:
   - Increase the threshold for more aggressive removal.
   - Decrease the threshold for more conservative removal.
   - Example:
     ```javascript
     const result = await spriteAI.removeBackground({
       image_file: "path/to/image.jpg",
       threshold: 0.7
     });
     ```

3. Try different models:
   - Experiment with different background removal models if available.
   - Example:
     ```javascript
     const result = await spriteAI.removeBackground({
       image_file: "path/to/image.jpg",
       model: "advanced"
     });
     ```

4. Post-process the result:
   - Consider using additional image processing tools to refine the result.

## API Interaction Errors

### Problem: API request failures

**Symptoms**: Requests to the SpriteAI API fail with error messages or timeouts.

**Solution**:

1. Check your API key:
   - Ensure your API key is valid and correctly set.
   - Example:
     ```javascript
     const spriteAI = new SpriteAI("your-api-key-here");
     ```

2. Verify network connectivity:
   - Check your internet connection.
   - Try accessing the API from a different network if possible.

3. Handle rate limiting:
   - Implement exponential backoff for retries.
   - Example:
     ```javascript
     const maxRetries = 3;
     let retryCount = 0;

     while (retryCount < maxRetries) {
       try {
         const result = await spriteAI.generateImage({
           prompt: "A cute cartoon robot"
         });
         break;
       } catch (error) {
         if (error.message.includes("rate limit")) {
           retryCount++;
           await new Promise(resolve => setTimeout(resolve, 1000 * Math.pow(2, retryCount)));
         } else {
           throw error;
         }
       }
     }
     ```

4. Check API status:
   - Visit the SpriteAI status page or contact support if issues persist.

## File Handling Difficulties

### Problem: Unable to save or load image files

**Symptoms**: Generated images cannot be saved, or existing images cannot be loaded for processing.

**Solution**:

1. Check file permissions:
   - Ensure your application has read/write permissions for the target directories.

2. Verify file paths:
   - Use absolute paths when possible.
   - Double-check the file extensions.
   - Example:
     ```javascript
     const path = require('path');
     const imagePath = path.resolve(__dirname, 'images', 'output.png');

     await spriteAI.saveImage(result, imagePath);
     ```

3. Handle file streams properly:
   - Close file streams after use.
   - Use try-catch blocks for file operations.
   - Example:
     ```javascript
     const fs = require('fs');

     try {
       const writeStream = fs.createWriteStream('output.png');
       await spriteAI.saveImage(result, writeStream);
       writeStream.end();
     } catch (error) {
       console.error('Error saving image:', error);
     }
     ```

4. Check available disk space:
   - Ensure there's enough free space on the disk for saving new images.

By following this troubleshooting guide, you should be able to resolve most common issues encountered when using the SpriteAI library. If problems persist, please consult the API documentation or contact SpriteAI support for further assistance.