# 🥭 Motion-controlled Fruit Slicer 3D game – A Hand-Tracking Game in the Browser

Welcome to **Motion-controlled 3D game**, a browser-based interactive game where you slice fruits (and avoid bombs!) using just your hand movements — powered by pose detection and 3D rendering.

This project combines computer vision and 3D graphics to create a fun and immersive experience directly in your browser.

---

## 🚀 Features

- Real-time **hand pose detection** using PoseNet
- 3D environment powered by **Three.js**
- Dynamic 3D fruit and bomb models
- Hand **trail animations** for visual effects
- **Collision detection** between hand and 3D objects
- Sound effects and game logic (score, lives, game over)
- Fully functional in-browser, with **no downloads needed**

---

## 🧠 Step 1: Breaking the Problem Down

To build this project, the process was broken down into manageable tasks:

1. Set up hand pose detection
2. Initialize and render a 3D scene
3. Load and display 3D fruit and bomb models
4. Map 2D hand coordinates to 3D space
5. Add hand trail animation
6. Enable collision detection
7. Implement game logic (scoring, sounds, game over)
8. Refactor and polish the codebase
9. Deploy the game to the web

---

## 🛠️ Step 2: Picking the Tools

| Task                      | Tool/Library                  |
|---------------------------|-------------------------------|
| Pose Detection            | [TensorFlow PoseNet](https://github.com/tensorflow/tfjs-models/tree/master/posenet) |
| 3D Rendering              | [Three.js](https://threejs.org/) |
| 3D Trail Effects          | [TrailRendererJS](https://github.com/mattdesl/trail-renderer) |
| Sound Management          | [Howler.js](https://howlerjs.com/) |
| Hosting                   | [Netlify](https://www.netlify.com/) |
| 3D Models                 | Assets from [Google Poly](https://poly.google.com/) (archived but usable) |

---

## 🛠️ Step 3: Setup & How to Run Locally

> ⚠️ Make sure you're serving this on a local server (due to webcam/media access). You can use `Live Server` in VS Code or Python's `http.server`.

### 1. Clone the Repository

git clone https://github.com/SusmoyNath/Motion-controlled-3D-game.git

cd Motion-controlled-3D-game


### 2. Open `index.html` in a local server

- **Option 1**: Use the Live Server extension in VS Code
- **Option 2**: Serve via Python


python3 -m http.server


Visit `http://localhost:8000` in your browser.

---

## 🎮 Gameplay Overview

- Your **hand becomes the slicer**.
- Slice fruits to earn points.
- Avoid bombs — slicing them ends the game.
- Trails follow your hand for added visual feedback.
- Enjoy sound effects and an immersive 3D environment.

---

## 🔍 Example Code Snippets

### PoseNet Initialization

```javascript
const net = await posenet.load({
  architecture: "MobileNetV1",
  outputStride: 16,
  inputResolution: 513,
  multiplier: 0.75,
});

video = await loadVideo();
detectPoseInRealTime(video);
```

### 3D Scene Setup with Three.js

```javascript
scene = new THREE.Scene();
camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 1, 1000);
camera.position.set(0, 0, 300);
scene.add(camera);
```

### Load and Render 3D Models

```javascript
objLoader.load("apple.obj", (object) => {
  object.position.set(0, 0, 100);
  scene.add(object);
});
```

---

## 🌐 Live Demo

> 🔗 **[Play the Game Here](https://splat.netlify.app/)**

---

## 📦 Deployment

This project is deployed using **Netlify**. Any updates pushed to the main branch are automatically deployed.

---

## 🙌 Acknowledgements

- [PoseNet](https://github.com/tensorflow/tfjs-models/tree/master/posenet)
- [Three.js](https://threejs.org/)
- [TrailRendererJS](https://github.com/mattdesl/trail-renderer)
- [Howler.js](https://howlerjs.com/)
- Assets from Poly, Sketchfab, and other open 3D model repositories

