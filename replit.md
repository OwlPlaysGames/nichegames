# Overview

BlazerGames is a static web-based games portal that hosts a collection of popular HTML5 games. The site serves as a centralized platform where users can access and play various games directly in their browser without requiring downloads or installations. The games collection includes popular titles like 1v1.LOL, 2048, Bob The Robber 2, Drive Mad, Moto X3M series, Vex series, Retro Bowl, and Slope.

The project is designed as a simple, lightweight gaming portal with a clean interface featuring game thumbnails and play buttons. It's optimized for easy deployment across multiple platforms and hosting services, making it accessible to a wide audience of casual gamers.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The site uses a traditional static web architecture with vanilla HTML, CSS, and JavaScript. The main entry point is `index.html` which displays a grid-style layout of featured games with thumbnail images and play buttons. The design uses modern CSS with Google Fonts (Montserrat) and Font Awesome icons for a clean, contemporary look.

Navigation is implemented through a fixed header with a logo and site title. The layout is responsive and uses flexbox/grid patterns for game thumbnails. Each game is represented by a clickable thumbnail that links to individual game directories.

## Game Structure
Each game is self-contained within its own directory under `/games/`. Games follow different architectural patterns:
- **Unity WebGL Games**: Games like 1v1.LOL use Unity's WebGL export with UnityLoader.js
- **Phaser.js Games**: Games like Bob The Robber 2 and Vex series use Phaser framework with minified game files
- **HTML5 Canvas Games**: Simple games like 2048 use vanilla JavaScript with HTML5 Canvas
- **Emscripten Games**: Games like Drive Mad use Emscripten to compile C/C++ to WebAssembly

Most games include:
- `index.html` as the game entry point
- Minified JavaScript game engine files
- Asset directories for images, audio, and game data
- CSS styling specific to each game
- Version control files for cache busting

## Server Architecture
The project includes a simple Python HTTP server (`server.py`) for local development. This server:
- Serves static files from the current directory
- Adds CORS headers for cross-origin requests
- Disables caching for development purposes
- Runs on port 5000 by default

The server is designed for development use and the site can be deployed as static files to any web server or CDN.

## Content Management
Games are organized in a simple directory structure where each game has its own folder. The main page manually references specific games with hardcoded links and images. There's no dynamic content management system - games are added by:
1. Creating a new directory under `/games/`
2. Adding the game files
3. Manually updating the main page HTML with new game links

# External Dependencies

## Game Engines and Frameworks
- **Unity WebGL**: Used for 3D games like 1v1.LOL, includes Unity runtime and loader
- **Phaser.js**: Popular 2D game framework used by multiple games
- **p2.js**: Physics engine used by some games
- **Emscripten/WebAssembly**: For compiled C/C++ games

## External Services
- **Google Fonts**: Montserrat font family loaded from fonts.googleapis.com
- **Font Awesome**: Icon library (version 6.2.0) loaded from site-assets.fontawesome.com
- **Game Distribution Networks**: Some games reference external CDNs and game distribution services
- **Analytics Services**: Games may include Google Analytics or other tracking services

## Development Tools
- **Python HTTP Server**: Built-in server for local development
- **Cache Busting**: Version control system for preventing browser caching issues during development

## Browser APIs
- **HTML5 Canvas**: For 2D graphics rendering
- **WebGL**: For 3D graphics and GPU acceleration
- **Web Audio API**: For game audio
- **LocalStorage**: For saving game progress and settings
- **Touch Events**: For mobile device support
- **Fullscreen API**: For immersive gaming experience

The architecture prioritizes simplicity and compatibility, avoiding complex build processes or server-side requirements to ensure easy deployment and maintenance.