# Image Organization Guide for Vercel Deployment

## Folder Structure

```
assets/
├── hero/                 # Hero section images
├── portfolio/            # Portfolio project images
├── testimonials/         # Client testimonial images
└── screenshots/          # Other UI images
```

## Best Practices for Vercel Deployment

### 1. **Image Optimization**
- Use modern formats: WebP, AVIF
- Responsive images with srcset
- Lazy loading for below-the-fold images
- Optimize file sizes before upload

### 2. **File Naming**
- Use descriptive names: `restaurant-campaign-hero.jpg`
- Use lowercase with hyphens: `NO_SPACES`
- Include dimensions: `project-1200x800.jpg`
- Avoid timestamps and special characters

### 3. **Vercel Optimization Tips**
- Enable Image Optimization: Vercel auto-optimizes on request
- Use relative paths: `/assets/hero/image.jpg`
- CDN caching: Images are cached globally
- Automatic format conversion: WebP for modern browsers

### 4. **HTML Implementation**
```html
<!-- Modern responsive image -->
<img 
  src="/assets/portfolio/project-1200x800.jpg"
  srcset="/assets/portfolio/project-600x400.jpg 600w,
          /assets/portfolio/project-1200x800.jpg 1200w"
  sizes="(max-width: 600px) 100vw, 1200px"
  alt="Project description"
  loading="lazy"
/>
```

### 5. **Performance Metrics**
- Target: <50KB per image
- Use compression tools before deployment
- JPG for photos
- PNG for graphics with transparency
- WebP for modern browsers

## Image Categories & Usage

### Hero Section
- **Location**: `/assets/hero/`
- **Size**: 1400x800px or larger
- **Format**: JPG or WebP
- **Files**: Main hero image, background elements

### Portfolio Projects
- **Location**: `/assets/portfolio/`
- **Size**: 1200x800px or 800x600px
- **Format**: JPG (photos), PNG (graphics)
- **Files**: project-1.jpg, project-2.jpg, etc.

### Testimonials/Reviews
- **Location**: `/assets/testimonials/`
- **Size**: 200x200px (avatars), 400x400px (full images)
- **Format**: JPG or PNG
- **Files**: avatar-1.jpg, client-photo-1.jpg

## Deployment Checklist

- [ ] Organize images in folders
- [ ] Rename images with descriptive names
- [ ] Compress images to <100KB
- [ ] Update HTML image paths
- [ ] Test responsive images
- [ ] Deploy to Vercel
- [ ] Monitor image load times
- [ ] Use Vercel Analytics for optimization

## Local Testing Before Deployment

```bash
# Test image paths locally
# Open browser and check Images Network tab
# Verify all images load correctly
# Check responsive behavior
```

## After Vercel Deployment

1. Images are automatically optimized
2. Global CDN caching enabled
3. Monitor performance:
   - Vercel Analytics → Web Vitals
   - Check LCP (Largest Contentful Paint)
   - Verify CLS (Cumulative Layout Shift)

## Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| Images not loading | Check path format, use absolute paths `/assets/...` |
| Slow load times | Compress images, use WebP format |
| Layout shift | Add `width` and `height` attributes |
| Responsive issues | Use `srcset` and `sizes` attributes |

## Tools for Optimization

- **Compression**: TinyPNG, ImageOptim, Squoosh
- **Conversion**: ImageMagick, Cloudinary
- **Validation**: WebPageTest, Lighthouse

---

**Note**: Replace placeholder images with your actual images and update paths accordingly.
