# Goodminds Loading Screen Flow

This project implements a seamless loading screen experience with 4 sequential screens that automatically transition between each other.

## Flow Overview

1. **Loading Screen (Logo)** - Shows the Goodminds logo for 2 seconds
2. **Loading Screen Progress** - Displays a progress counter from 0-99% over 3 seconds
3. **Loading Screen Interactive** - Shows animated bubbles with interactive elements for 4 seconds
4. **Loading Screen Quote** - Displays an inspirational quote for 5 seconds
5. **Welcome Screen** - Shows welcome message and "Get Started" button (stays until user interaction)

## How to Use

1. Open `index.html` in your web browser
2. The loading sequence will automatically start
3. Each screen will transition to the next after its designated time
4. The sequence will complete after the quote screen

## Features

### Progress Screen
- Real-time progress counter from 0 to 100%
- Smooth progress bar animation
- Overlay that appears during the progress screen

### Interactive Screen
- Floating bubble animations with different timing
- Mouse/touch interaction that moves bubbles
- Pulsing text effects
- Shake animation for interaction prompts

### Auto-Navigation
- Automatic transitions between screens
- Configurable timing for each screen
- Smooth transitions with CSS animations

## File Structure

```
Goodminds/
├── index.html                    # Main entry point with auto-navigation
├── loading-logo/                # Screen 1: Logo display
├── loading-progress/            # Screen 2: Progress counter
├── loading-interactive/         # Screen 3: Interactive bubbles
├── loading-quote/               # Screen 4: Inspirational quote
└── welcome-screen/              # Screen 5: Welcome screen
```

## Customization

### Timing Configuration
You can modify the screen timings in `index.html`:

```javascript
const screenTimings = {
  1: 2000,  // Logo screen: 2 seconds
  2: 3000,  // Progress screen: 3 seconds
  3: 4000,  // Interactive screen: 4 seconds
  4: 5000,  // Quote screen: 5 seconds
  5: 0      // Welcome screen: stay until user interaction
};
```

### Progress Speed
Adjust the progress counter speed by changing the interval in the `startProgress()` function:

```javascript
progressInterval = setInterval(() => {
  progress += 1;
  updateProgress();
  
  if (progress >= 100) {
    clearInterval(progressInterval);
  }
}, 30); // Update every 30ms for smooth animation
```

### Bubble Animations
The interactive screen includes floating animations for the bubbles. You can modify the animation timing and effects in the CSS keyframes.

## Browser Compatibility

- Modern browsers with CSS3 and ES6 support
- Mobile-responsive design
- Touch interaction support for mobile devices

## Next Steps

After the loading sequence completes, you can:
1. Redirect to your main application
2. Show a "Get Started" button
3. Continue with additional onboarding screens

To redirect to a main app, uncomment and modify this line in `index.html`:
```javascript
window.location.href = './main-app.html';
``` 