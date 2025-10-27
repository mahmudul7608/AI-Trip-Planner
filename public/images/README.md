# Images & Videos Folder

This folder is for storing static assets like images and videos for the AI Trip Planner project.

## How to Use:

1. **Add your files here**: Place your images (jpg, png, gif, etc.) and videos (mp4, webm, etc.) in this folder

2. **Access them in your code**:

   ```vue
   <!-- For images -->
   <img src="/images/your-image.jpg" alt="Description" />

   <!-- For videos -->
   <video src="/images/your-video.mp4" controls></video>
   ```

3. **In CSS/Tailwind**:
   ```css
   background-image: url("/images/your-background.jpg");
   ```

## Supported Formats:

- **Images**: JPG, PNG, GIF, WebP, SVG
- **Videos**: MP4, WebM, OGG

## Note:

- Files in the `public` folder are served at the root level
- Access them using `/images/filename.ext`
- Keep file sizes optimized for better performance
