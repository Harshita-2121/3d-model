# Jean Marais GLB hosting files (model intentionally not included)

This package contains the Render static-site configuration and instructions only. It does **not** include a 3D model file.

## Before deploying

1. Put your own compressed, working GLB model in the `public` folder.
2. Rename that file to exactly `face.glb`, so the path is `public/face.glb`.
3. Confirm that `face.glb` is smaller than 2,000,000 bytes.
4. Upload the contents of this package, including `render.yaml`, `README.md`, and `public/face.glb`, to the root of your GitHub repository. `render.yaml` must be at the repository root.
5. In Render, select **New → Blueprint**, connect the repository, and deploy the `jean-marais-face` static site.
6. After deployment, test the direct file URL: `https://YOUR-SERVICE.onrender.com/face.glb` (replace `YOUR-SERVICE` with your actual Render hostname).

## Verify headers

Run this in PowerShell, replacing the hostname:

```powershell
curl.exe -I https://YOUR-SERVICE.onrender.com/face.glb
```

The response should be HTTP `200 OK` and include `Access-Control-Allow-Origin: *`. The file should be served directly, not through a viewer page.

Do not submit the Render root URL. Submit the direct URL ending in `/face.glb`.
