# Space Invaders - Mobile Game

A faithful recreation of the classic Space Invaders arcade game, optimized for mobile devices.

## How to Play

Open `space-invaders.html` in any modern web browser on your mobile device or desktop.

### Controls

**Mobile:**
- **◄ Button**: Move left
- **► Button**: Move right
- **FIRE Button**: Shoot

**Desktop/Keyboard:**
- **Arrow Left**: Move left
- **Arrow Right**: Move right
- **Spacebar**: Shoot
- **Enter**: Start game

### Gameplay

- Destroy all invaders to advance to the next level
- Invaders move side to side and gradually descend
- Hide behind barriers for protection (they can be destroyed)
- Invaders shoot back - avoid their bullets!
- You have 3 lives - don't let the invaders reach you
- Each invader type has different point values:
  - Top row (squid): 30 points
  - Middle rows (crab): 20 points
  - Bottom rows (octopus): 10 points

## Features

- **Classic Arcade Style**: Green monochrome graphics with pixel-perfect rendering
- **Mobile Optimized**: Touch controls and responsive design
- **Progressive Difficulty**: Invaders speed up as you destroy them and advance levels
- **Sound Effects**: Retro-style sound effects using Web Audio API
- **High Score**: Your best score is saved locally
- **Destructible Barriers**: Classic shield protection that degrades with hits
- **Authentic Mechanics**: Faithful recreation of the original game behavior

## Technical Details

- Pure HTML5, CSS3, and JavaScript
- Canvas-based rendering
- Responsive design that works on any screen size
- No external dependencies
- Local storage for high score persistence

## Browser Compatibility

Works on all modern browsers that support:
- HTML5 Canvas
- Web Audio API
- Local Storage

Tested on Chrome, Firefox, Safari, and Edge.

## Game Over

When you lose all lives or invaders reach the bottom, the game ends. Your high score is automatically saved. Tap/click to restart and try to beat your record!
