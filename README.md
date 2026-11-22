# KeyShotXR Instructions

How to create an interactive 360° product viewer (KeyShotXR) from a KeyShot scene.

## What is KeyShotXR?
KeyShotXR renders a set of images around your model (and optionally above/below it) and packages them into an interactive viewer. Viewers can drag to rotate the product, and the output embeds in a web page.

## 1. Prepare the scene
1. Finish materials, lighting, environment and camera in KeyShot.
2. Place the model at the center of the scene. Use **Move Tool / Model > Position** to set the pivot where you want the rotation axis.
3. Lock the camera (Camera tab > lock) so the framing stays constant.
4. Set a clean background (solid color or transparent, if using a PNG-based output).

## 2. Open the XR setup
1. Go to **Render > Output > KeyShotXR** (in some versions: **Render > KeyShotXR**).
2. Choose the viewer type:
   - **Horizontal rotation** – a single ring around the product (turntable).
   - **Horizontal + vertical** – a sphere of views, drag in any direction.

## 3. Settings
| Setting | Recommendation |
|---|---|
| Frames (horizontal) | 36 for fast loading, 72 for smooth rotation |
| Frames (vertical) | 5–9 if using vertical rotation |
| Resolution | 1000–1600 px square for web; keep file size reasonable |
| Format | JPEG for small files; PNG if you need transparency |
| Samples / render quality | 64–128 samples for final output |
| Rotation direction / start angle | Set to the camera's hero view |

## 4. Render
1. Click **Render** and choose the output folder.
2. KeyShot renders all frames and builds the XR package (HTML, JS, images, `.xr` data).
3. Preview the viewer in the KeyShotXR window before closing.

## 5. Publish / embed
1. Upload the whole output folder to your web host (or this repo via GitHub Pages).
2. Embed in a page:
   ```html
   <iframe src="keyshotxr/index.html" width="800" height="800" frameborder="0"></iframe>
   ```
3. Or use the **KeyShot Cloud** upload option, if your license includes it.

## Tips
- Keep the model and lighting identical across frames – do not animate lights.
- Use ground shadows or a floor for realism; avoid reflections that reveal the camera.
- Test on mobile; lower the frame count or resolution if loading is slow.
- Name folders without spaces for reliable web paths.

## Repo layout (suggested)
```
/README.md          this guide
/viewer/            exported KeyShotXR folder (index.html, images)
/scenes/            .bip scene files
```
