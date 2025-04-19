# Three.js Memory Card Game

A simple, visually engaging memory matching game built using HTML, CSS, JavaScript, and the Three.js library. Players interact with a 3D grid of cards, attempting to find all the matching pairs against an animated underwater background.

## Features

* **3D Card Rendering:** Uses Three.js to display cards as 3D planes in a grid layout.
* **Smooth Animations:** Cards feature a smooth flipping animation when clicked.
* **Interactive Gameplay:** Click on cards to reveal their images and find matches.
* **Game Logic:**
    * 5x5 grid (25 cards).
    * Uses 12 unique images, creating 12 pairs to match. One card will remain unmatched.
    * Tracks the player's score (number of matches found).
    * Tracks the number of attempts made.
* **UI Elements:**
    * Displays current score and attempts.
    * "Reset Game" button to shuffle and start over.
    * Completion message when all pairs are found.
* **Visuals & Sound:**
    * Animated underwater-themed gradient background with bubble effects using CSS.
    * Sound effects for flipping a card (`flip.mp3`) and finding a match (`match.mp3`).
* **Responsive Layout:** Basic responsiveness for the game board container.

## Technologies Used

* HTML5
* CSS3 (including @keyframes animations)
* JavaScript (ES6)
* Three.js (r128, loaded via CDN)

## How to Play

1.  The game presents a 5x5 grid of face-down cards.
2.  Click on a card to flip it over and reveal the image.
3.  Click on a second card to reveal its image.
4.  **If the images match:** The cards remain face-up, and your score increases by one. You will hear a match sound.
5.  **If the images do not match:** The cards will flip back face-down after a short delay.
6.  Each pair of revealed cards counts as one attempt.
7.  The goal is to find all 12 matching pairs. The game is won when 12 matches are made. The single remaining card does not need to be matched.
8.  A success message will appear when you complete the game, showing your total attempts.
9.  Click the "Reset Game" button at any time to shuffle the cards and start a new game.

## Setup and Installation

To run this game locally, follow these steps:

1.  **Download/Clone:** Get the project files (HTML file).
2.  **Create Asset Folders:**
    * Create an `img` folder in the same directory as the HTML file.
    * Place your 12 card images inside the `img` folder. The code expects them to be named like `img-1.webp`, `img-2.jpg`, ..., `img-12.jpg`. You can modify the `imagePool` array in the JavaScript code if your filenames differ.
3.  **Add Sound Files:**
    * Place the sound files `flip.mp3` and `match.mp3` in the same directory as the HTML file.
4.  **Run a Local Server:**
    * Because the game loads local resources (textures, audio) using JavaScript, you need to run it through a local web server to avoid browser security restrictions (CORS errors).
    * **Option A (Node.js):** If you have Node.js installed, open your terminal in the project directory and run: `npx serve`
    * **Option B (Python 3):** If you have Python installed, open your terminal in the project directory and run: `python -m http.server`
    * **Option C (VS Code):** Use the "Live Server" extension.
5.  **Access the Game:** Open your web browser and navigate to the local address provided by the server (e.g., `http://localhost:3000`, `http://localhost:8080`, or `http://127.0.0.1:5500` for Live Server).

## File Structure

*   `index.html`: The main HTML file containing the game's structure and JavaScript code.
*   `img/`: Folder containing the card images.
*   `flip.mp3`: Sound effect for flipping a card.
*   `match.mp3`: Sound effect for finding a match.

## Notes

* The game requires an active internet connection to load the Three.js library from the CDN.
* The 5x5 grid means there is one card that does not have a matching pair; this is handled by the win condition (`Math.floor(25/2)` pairs).
* Sound playback might be restricted by some browsers until the user interacts with the page (e.g., clicks).
