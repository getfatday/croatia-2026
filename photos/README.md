# Trip photos

Drop photos from the trip in this folder and they'll show up on the matching
day in the itinerary.

## Synced from Google Drive

Photos are imported from the shared **Croatia** Google Drive folder. Each file
keeps its original camera name (`IMG_####.jpg`), so the filename is the key we
track by — when new photos are added to Drive, we only import the names that
aren't already in this folder. Originals are HEIC; they're converted to JPG,
auto-rotated, and resized to ~1600px on the long edge (quality ~82) for the web.

Each photo is filed onto the trip day that matches its EXIF capture date.

## How to add a photo

1. **Add the image file here**, in `photos/`. Use a name that says which day it
   belongs to, e.g. `jun1-supetar.jpg`, `may31-marjan-1.jpg`. Phone photos
   (JPG/PNG/HEIC→JPG) are fine — resize to ~1600px on the long edge to keep the
   page fast.

2. **Register it** in `index.html`, in the `TRIP_PHOTOS` block near the bottom
   of the file. Add one line under the right day:

   ```js
   const TRIP_PHOTOS = {
     ...
     jun1: [
       { src: 'photos/jun1-supetar.jpg', caption: 'Sunset over Supetar harbor' },
       { src: 'photos/jun1-skrip.jpg',   caption: 'Olive oil museum in Škrip' }
     ],
     ...
   };
   ```

   - `src` is the path to the file (always starts with `photos/`).
   - `caption` shows under the photo in the lightbox. Keep it short, or use `''`.

3. **Commit and push.** A photo grid appears on that day automatically; tap any
   photo to open it full-screen.

## Notes

- Days that have already happened but have no photos yet show a small
  "📸 Photos coming soon" placeholder. Future days stay clean until there's
  something to show.
- Order in the array = order on the page.
