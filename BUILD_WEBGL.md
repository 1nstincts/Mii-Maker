# Building Mii Maker for WebGL

To play Mii Maker in your web browser, you need to build it as a WebGL application using Unity.

## Prerequisites

1. Unity 2021.3 or later installed
2. WebGL Build Support module installed in Unity

## Build Steps

1. **Open the project in Unity**
   - Launch Unity Hub
   - Click "Add" and select the Mii-Maker folder
   - Open the project with Unity 2021.3 or later

2. **Switch to WebGL Platform**
   - Go to `File → Build Settings`
   - Select "WebGL" from the platform list
   - Click "Switch Platform" (this may take a few minutes)

3. **Configure WebGL Settings**
   - Click "Player Settings"
   - Under WebGL settings:
     - Set Compression Format to "Gzip" or "Disabled" for GitHub Pages
     - Set WebGL Memory Size to 512 or 1024
     - Enable "Data Caching" for better performance

4. **Build the Project**
   - In Build Settings, click "Build"
   - Create a new folder called "WebGLBuild" in the project root
   - Select this folder and click "Select Folder"
   - Wait for the build to complete (this can take 10-30 minutes)

5. **Deploy to GitHub Pages**
   - Copy all files from the WebGLBuild folder
   - Create a new branch called `gh-pages` in your repository
   - Upload all the WebGL build files to the root of the `gh-pages` branch
   - Commit and push the changes

6. **Configure GitHub Pages**
   - Go to Settings → Pages in your GitHub repository
   - Set Source to "Deploy from a branch"
   - Select the `gh-pages` branch and root folder
   - Save the settings

Your game will be playable at your GitHub Pages URL after a few minutes!

## Alternative: Local Testing

To test locally:
1. After building, install a local web server:
   ```bash
   npm install -g http-server
   ```
2. Navigate to your build folder:
   ```bash
   cd WebGLBuild
   ```
3. Start the server:
   ```bash
   http-server -c-1
   ```
4. Open http://localhost:8080 in your browser

## Troubleshooting

- **Build fails**: Make sure you have enough disk space (WebGL builds can be large)
- **Compression issues**: GitHub Pages works best with Gzip or no compression
- **Memory errors**: Increase the WebGL Memory Size in Player Settings
- **Loading issues**: Make sure all files are uploaded correctly to gh-pages branch