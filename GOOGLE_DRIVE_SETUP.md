# Google Drive Video Setup Instructions

## How to Get Google Drive Video IDs

1. **Upload your videos to Google Drive**
2. **Make videos publicly viewable:**
   - Right-click on each video file
   - Select "Share"
   - Click "Change to anyone with the link"
   - Set permission to "Viewer"
   - Copy the sharing link

3. **Extract the File ID from the sharing link:**
   - Google Drive link format: `https://drive.google.com/file/d/FILE_ID_HERE/view?usp=sharing`
   - Copy the `FILE_ID_HERE` part

## Update the VideoGallery Component

Edit `src/components/VideoGallery.astro` and replace the placeholder video data:

```javascript
const videos: VideoItem[] = [
  {
    id: "1",
    title: "Your Video Title 1",
    description: "Description of your first video",
    thumbnail: "/path/to/thumbnail1.jpg", // Optional: Add custom thumbnails
    driveId: "REPLACE_WITH_ACTUAL_GOOGLE_DRIVE_FILE_ID", 
    category: "voice" // or "visual", "motion", "custom"
  },
  {
    id: "2",
    title: "Your Video Title 2", 
    description: "Description of your second video",
    thumbnail: "/path/to/thumbnail2.jpg",
    driveId: "REPLACE_WITH_ACTUAL_GOOGLE_DRIVE_FILE_ID",
    category: "visual"
  },
  // Add more videos as needed
];
```

## Video Categories

Use these categories for filtering:
- `voice` - AI Voice Synthesis videos
- `visual` - Visual Creation/Image Generation videos  
- `motion` - Motion Graphics/Video Production videos
- `custom` - Custom Solutions/Enterprise videos

## Custom Thumbnails (Optional)

1. Create thumbnail images (recommended: 400x225px, 16:9 aspect ratio)
2. Add them to your `public` folder
3. Update the `thumbnail` property with the path: `/thumbnails/video1.jpg`

## Testing

1. Make sure your Google Drive videos are set to "Anyone with the link can view"
2. Test the embed URL format: `https://drive.google.com/file/d/YOUR_FILE_ID/preview`
3. The lightbox should open when clicking on video cards
4. Videos should play directly in the lightbox modal

## Example with Real Data

```javascript
const videos: VideoItem[] = [
  {
    id: "1",
    title: "AI Voice Demo - Customer Service",
    description: "Professional AI voice generation for customer service applications",
    thumbnail: "/thumbnails/voice-demo.jpg",
    driveId: "1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms", // Example ID
    category: "voice"
  }
];
```

## Troubleshooting

- **Video not loading**: Check if the Google Drive file is publicly accessible
- **Thumbnail not showing**: Verify the image path is correct and file exists in public folder
- **Lightbox not opening**: Check browser console for JavaScript errors
- **Video quality**: Google Drive automatically adjusts quality based on connection speed
