# DEDSEC // ROUGER - Animated Cyberpunk Landing Page

![Cyberpunk Animated Background](https://img.shields.io/badge/Animation-Cyberpunk-00f2ff?style=for-the-badge)
![Technology Stack](https://img.shields.io/badge/Stack-HTML%20%7C%20CSS%20%7C%20JavaScript-ff00ff?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-39ff14?style=for-the-badge)

A sophisticated cyberpunk-themed animated landing page featuring dynamic particle networks, glitch effects, and real-time system status displays. Built for high-performance deployment on static hosting platforms like Vercel.

## 📑 Table of Contents

- [🌐 Live Demo](#-live-demo)
- [🎨 Visual Overview](#-visual-overview)
  - [📸 Screenshots](#-screenshots)
- [🚀 Features](#-features)
  - [Core Animations](#core-animations)
  - [Technical Highlights](#technical-highlights)
- [📁 Project Structure](#-project-structure)
- [🎬 Animation Breakdown](#-animation-breakdown)
  - [1. Chaotic Glitch Animation](#1-chaotic-glitch-animation)
  - [2. Network Node Visualization](#2-network-node-visualization)
  - [3. Threat Detection Radar](#3-threat-detection-radar)
  - [4. Encryption Activity Bar](#4-encryption-activity-bar)
  - [5. Firewall Status Indicator](#5-firewall-status-indicator)
  - [6. Data Packet Flow](#6-data-packet-flow)
  - [7. Breach Alert System](#7-breach-alert-system)
  - [8. System Status Monitor](#8-system-status-monitor)
  - [9. Interactive Parallax](#9-interactive-parallax)
  - [10. Typewriter Terminal](#10-typewriter-terminal)
- [🎨 Color Palette](#-color-palette)
- [🏗️ Technology Stack](#️-technology-stack)
- [⚡ Performance Optimizations](#-performance-optimizations)
- [🎯 Browser Support](#-browser-support)
- [🚀 Deployment](#-deployment)
- [🔧 Configuration](#-configuration)
- [📐 Z-Index Architecture](#-z-index-architecture)
- [🔍 Debug Mode](#-debug-mode)
- [📄 License](#-license)
- [🤝 Contributing](#-contributing)
- [📞 Support](#-support)
- [🌟 Acknowledgments](#-acknowledgments)
- [📈 Changelog](#-changelog)

## 🌐 Live Demo

[![Live Demo](https://img.shields.io/badge/Live%20Demo-View%20Now-00f2ff?style=for-the-badge)](https://animated-bg-watchdog.vercel.app/)
[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-ff00ff?style=for-the-badge)](https://github.com/praveensaummya)

**Live URL**: https://animated-bg-watchdog.vercel.app/  
**GitHub**: https://github.com/praveensaummya

## 🎨 Visual Overview

![Cyberpunk Interface Screenshot](screenshots/hero-screenshot.png)

*Dynamic cyberpunk interface with animated network nodes, glitching logo, and real-time system status*


## 🚀 Features

1. **Chaotic Glitch System** - Dynamic logo distortion with displacement mapping
2. **Network Node Visualization** - Animated particle network with pulsing connections
3. **Threat Detection Radar** - Simulated security scanning interface
4. **Encryption Activity Monitor** - Real-time data encryption visualization
5. **Firewall Status Indicator** - Vertical security status display
6. **Data Packet Flow** - Animated network packet transmission
7. **Breach Alert System** - Random security breach notifications
8. **System Status Monitor** - Live node and connection statistics
9. **Interactive Parallax** - Mouse-responsive 3D logo transformation
10. **Typewriter Terminal** - Simulated command-line interface

### Technical Highlights

- ✅ **Zero Dependencies** - Pure vanilla JavaScript
- ✅ **High Performance** - Optimized animation loops
- ✅ **Responsive Design** - Adapts to all screen sizes
- ✅ **Vercel Optimized** - SSR caching prevention built-in
- ✅ **Accessibility** - Semantic HTML structure
- ✅ **Cross-Browser** - Modern browser support

## 📁 Project Structure

```
animated-bg/
├── index.html              # Main application file
├── vercel.json            # Vercel deployment configuration
├── README.md              # This file
└── LICENSE                # MIT License
```

## 🎬 Animation Breakdown

### 1. Chaotic Glitch Animation

**Technology**: Anime.js + SVG Filters

**Description**: Dynamic logo distortion using SVG turbulence filters and displacement mapping.

**Implementation**:
```javascript
const timeline = anime.timeline({
    easing: 'steps(2)',
    complete: () => setTimeout(glitchLoop, anime.random(2000, 5000))
});

timeline
    .add({ targets: dispMap, scale: [0, 25, 0, 15, 0], duration: 300 })
    .add({ targets: '#dedsec-logo', opacity: [0.6, 0.95, 0.4, 0.95, 0.6], duration: 200, offset: 0 })
    .add({ targets: logoWrapper, translateX: [...], translateY: [...], offset: 0 })
    .add({ targets: [ghostV, ghostW], stroke: [...], opacity: [...], duration: 300, offset: 0 })
    .add({ targets: [logoV, logoW], stroke: [...], opacity: [1, 0.8, 1], duration: 120, offset: 0 });
```

**Key Features**:
- Random timing intervals (2-5 seconds)
- Multi-axis displacement effects
- Color cycling between red/cyan/green
- Opacity fluctuations for ghosting effects

### 2. Network Node Visualization

**Technology**: SVG + Vanilla JavaScript

**Description**: Dynamic particle network with 4 configurable cluster patterns.

**Cluster Patterns**:
```javascript
const clusterPatterns = [
    { nodeCount: 8,  connectionDistance: 180, pulseChance: 0.5 },  // Dense
    { nodeCount: 12, connectionDistance: 250, pulseChance: 0.4 },  // Spread
    { nodeCount: 6,  connectionDistance: 150, pulseChance: 0.6 },  // Tight
    { nodeCount: 10, connectionDistance: 200, pulseChance: 0.45 }  // Balanced
];
```

**Animation Loop**:
```javascript
function pulseNodes() {
    nodes.forEach((node, idx) => {
        if (Math.random() > pattern.pulseChance) {
            anime({
                targets: node.element,
                opacity: [0.1, 0.6, 0.1],
                r: [node.r, node.r * 1.8, node.r],
                duration: 800 + Math.random() * 600,
                easing: 'easeInOutSine'
            });
        }
    });
    nodePulseInterval = setTimeout(pulseNodes, 1500 + Math.random() * 1500);
}
```

**Pattern Cycling**:
- Initial display: 3.5 seconds
- Pattern duration: 3-4 seconds
- Transition speed: 1-2 seconds (faster)
- Automatic pattern randomization

### 3. Threat Detection Radar

**Technology**: CSS Animations + DOM Manipulation

**Description**: Simulated security scanning with animated radar sweeps and threat indicators.

**Implementation**:
```javascript
function createRadarSweep() {
    const sweep = document.createElement('div');
    sweep.className = 'radar-sweep';
    sweep.style.animation = 'radarPulse 4s ease-out infinite';
    threatRadar.appendChild(sweep);
    
    setTimeout(() => sweep.remove(), 4000);
}

setInterval(createRadarSweep, 5000);
```

**CSS Animation**:
```css
@keyframes radarPulse {
    0% { transform: scale(0.8); opacity: 0.8; }
    100% { transform: scale(2.5); opacity: 0; }
}
```

### 4. Encryption Activity Bar

**Technology**: CSS Keyframes + JavaScript

**Description**: Visual representation of real-time data encryption with randomized timing.

**Implementation**:
```javascript
for (let i = 0; i < 32; i++) {
    const block = document.createElement('div');
    block.className = 'encryption-block';
    block.style.animationDelay = (Math.random() * 2) + 's';
    encryptionBar.appendChild(block);
}
```

**Animation**:
```css
@keyframes encryptFlash {
    0%, 100% { opacity: 0.3; }
    50% { opacity: 1; }
}
```

### 5. Firewall Status Indicator

**Technology**: CSS Writing Mode + Static Content

**Description**: Vertical text display showing security status.

**CSS**:
```css
.firewall-status {
    writing-mode: vertical-rl;
    text-orientation: mixed;
    opacity: 0.3;
    color: var(--neon-green);
}
```

### 6. Data Packet Flow

**Technology**: CSS Animations + DOM Manipulation

**Description**: Animated network packets simulating data transmission.

**Implementation**:
```javascript
function createDataPacket() {
    const packet = document.createElement('div');
    packet.className = 'packet';
    packet.style.left = Math.random() * 100 + 'vw';
    packet.style.top = Math.random() * 100 + 'vh';
    packet.style.animation = `packetFlow ${2 + Math.random() * 2}s ease-in-out infinite`;
    
    document.body.appendChild(packet);
    setTimeout(() => packet.remove(), 5000);
}

setInterval(createDataPacket, 3000);
```

**Animation**:
```css
@keyframes packetFlow {
    0% { opacity: 0; transform: scale(0); }
    50% { opacity: 1; }
    100% { opacity: 0; transform: scale(1); }
}
```

### 7. Breach Alert System

**Technology**: Anime.js + DOM Manipulation

**Description**: Random security breach notifications with slide-in effects.

**Implementation**:
```javascript
function triggerBreachAlert() {
    const alert = document.createElement('div');
    alert.textContent = '>>> Security Breach Detected <<<';
    
    anime({
        targets: alert,
        opacity: [0, 0.8, 0],
        translateX: [-20, 0, 0],
        duration: 3000,
        easing: 'easeInOutSine',
        complete: () => alert.remove()
    });
}

setInterval(() => {
    if (Math.random() > 0.7) triggerBreachAlert();
}, 15000);
```

### 8. System Status Monitor

**Technology**: Vanilla JavaScript + DOM

**Description**: Real-time display of network statistics.

**Implementation**:
```javascript
function createSystemStatus() {
    const status = document.createElement('div');
    status.innerHTML = 
        'SYSTEM: ONLINE<br>' +
        'NODES: ' + nodes.length + '<br>' +
        'CONNS: ' + connections.length + '<br>' +
        'STATUS: SECURE';
    document.body.appendChild(status);
}
```

### 9. Interactive Parallax

**Technology**: Mouse Events + CSS Transforms

**Description**: 3D logo transformation based on mouse position.

**Implementation**:
```javascript
document.addEventListener('mousemove', (e) => {
    const moveX = (e.clientX / window.innerWidth - 0.5) * 8;
    const moveY = (e.clientY / window.innerHeight - 0.5) * 8;
    
    logo.parentElement.style.transform = 
        `translate(${moveX * -0.2}px, ${moveY * -0.2}px) ` +
        `rotateX(${moveY * 0.1}deg) rotateY(${moveX * -0.1}deg)`;
});
```

### 10. Typewriter Terminal

**Technology**: Vanilla JavaScript + setTimeout

**Description**: Simulated command-line interface with typing effect.

**Implementation**:
```javascript
function typeHead() {
    if (headIdx < headText.length) {
        headEl.textContent += headText.charAt(headIdx);
        headIdx++;
        setTimeout(typeHead, 80);
    } else {
        setTimeout(() => { 
            headEl.textContent = ""; 
            headIdx = 0; 
            typeHead(); 
        }, 8000);
    }
}
```
animated-bg/
├── index.html              # Main application file
├── vercel.json            # Vercel deployment configuration
├── README.md              # This file
├── FIX_SUMMARY.md         # Vercel fix documentation
├── LAYER_STRUCTURE.md     # Z-index architecture
└── FINAL_IMPLEMENTATION.md # Complete implementation guide
```

## 🎬 Animation Breakdown

### 1. Chaotic Glitch Animation

**Technology**: Anime.js + SVG Filters

**Description**: Dynamic logo distortion using SVG turbulence filters and displacement mapping.

**Implementation**:
```javascript
const timeline = anime.timeline({
    easing: 'steps(2)',
    complete: () => setTimeout(glitchLoop, anime.random(2000, 5000))
});

timeline
    .add({ targets: dispMap, scale: [0, 25, 0, 15, 0], duration: 300 })
    .add({ targets: '#dedsec-logo', opacity: [0.6, 0.95, 0.4, 0.95, 0.6], duration: 200, offset: 0 })
    .add({ targets: logoWrapper, translateX: [...], translateY: [...], offset: 0 })
    .add({ targets: [ghostV, ghostW], stroke: [...], opacity: [...], duration: 300, offset: 0 })
    .add({ targets: [logoV, logoW], stroke: [...], opacity: [1, 0.8, 1], duration: 120, offset: 0 });
```

**Key Features**:
- Random timing intervals (2-5 seconds)
- Multi-axis displacement effects
- Color cycling between red/cyan/green
- Opacity fluctuations for ghosting effects

### 2. Network Node Visualization

**Technology**: SVG + Vanilla JavaScript

**Description**: Dynamic particle network with 4 configurable cluster patterns.

**Cluster Patterns**:
```javascript
const clusterPatterns = [
    { nodeCount: 8,  connectionDistance: 180, pulseChance: 0.5 },  // Dense
    { nodeCount: 12, connectionDistance: 250, pulseChance: 0.4 },  // Spread
    { nodeCount: 6,  connectionDistance: 150, pulseChance: 0.6 },  // Tight
    { nodeCount: 10, connectionDistance: 200, pulseChance: 0.45 }  // Balanced
];
```

**Animation Loop**:
```javascript
function pulseNodes() {
    nodes.forEach((node, idx) => {
        if (Math.random() > pattern.pulseChance) {
            anime({
                targets: node.element,
                opacity: [0.1, 0.6, 0.1],
                r: [node.r, node.r * 1.8, node.r],
                duration: 800 + Math.random() * 600,
                easing: 'easeInOutSine'
            });
        }
    });
    nodePulseInterval = setTimeout(pulseNodes, 1500 + Math.random() * 1500);
}
```

**Pattern Cycling**:
- Initial display: 3.5 seconds
- Pattern duration: 3-4 seconds
- Transition speed: 1-2 seconds
- Automatic pattern randomization

### 3. Threat Detection Radar

**Technology**: CSS Animations + DOM Manipulation

**Description**: Simulated security scanning with animated radar sweeps and threat indicators.

**Implementation**:
```javascript
function createRadarSweep() {
    const sweep = document.createElement('div');
    sweep.className = 'radar-sweep';
    sweep.style.animation = 'radarPulse 4s ease-out infinite';
    threatRadar.appendChild(sweep);
    
    setTimeout(() => sweep.remove(), 4000);
}

setInterval(createRadarSweep, 5000);
```

**CSS Animation**:
```css
@keyframes radarPulse {
    0% { transform: scale(0.8); opacity: 0.8; }
    100% { transform: scale(2.5); opacity: 0; }
}
```

### 4. Encryption Activity Bar

**Technology**: CSS Keyframes + JavaScript

**Description**: Visual representation of real-time data encryption with randomized timing.

**Implementation**:
```javascript
for (let i = 0; i < 32; i++) {
    const block = document.createElement('div');
    block.className = 'encryption-block';
    block.style.animationDelay = (Math.random() * 2) + 's';
    encryptionBar.appendChild(block);
}
```

**Animation**:
```css
@keyframes encryptFlash {
    0%, 100% { opacity: 0.3; }
    50% { opacity: 1; }
}
```

### 5. Firewall Status Indicator

**Technology**: CSS Writing Mode + Static Content

**Description**: Vertical text display showing security status.

**CSS**:
```css
.firewall-status {
    writing-mode: vertical-rl;
    text-orientation: mixed;
    opacity: 0.3;
    color: var(--neon-green);
}
```

### 6. Data Packet Flow

**Technology**: CSS Animations + DOM Manipulation

**Description**: Animated network packets simulating data transmission.

**Implementation**:
```javascript
function createDataPacket() {
    const packet = document.createElement('div');
    packet.className = 'packet';
    packet.style.left = Math.random() * 100 + 'vw';
    packet.style.top = Math.random() * 100 + 'vh';
    packet.style.animation = `packetFlow ${2 + Math.random() * 2}s ease-in-out infinite`;
    
    document.body.appendChild(packet);
    setTimeout(() => packet.remove(), 5000);
}

setInterval(createDataPacket, 3000);
```

**Animation**:
```css
@keyframes packetFlow {
    0% { opacity: 0; transform: scale(0); }
    50% { opacity: 1; }
    100% { opacity: 0; transform: scale(1); }
}
```

### 7. Breach Alert System

**Technology**: Anime.js + DOM Manipulation

**Description**: Random security breach notifications with slide-in effects.

**Implementation**:
```javascript
function triggerBreachAlert() {
    const alert = document.createElement('div');
    alert.textContent = '>>> Security Breach Detected <<<';
    
    anime({
        targets: alert,
        opacity: [0, 0.8, 0],
        translateX: [-20, 0, 0],
        duration: 3000,
        easing: 'easeInOutSine',
        complete: () => alert.remove()
    });
}

setInterval(() => {
    if (Math.random() > 0.7) triggerBreachAlert();
}, 15000);
```

### 8. System Status Monitor

**Technology**: Vanilla JavaScript + DOM

**Description**: Real-time display of network statistics.

**Implementation**:
```javascript
function createSystemStatus() {
    const status = document.createElement('div');
    status.innerHTML = 
        'SYSTEM: ONLINE<br>' +
        'NODES: ' + nodes.length + '<br>' +
        'CONNS: ' + connections.length + '<br>' +
        'STATUS: SECURE';
    document.body.appendChild(status);
}
```

### 9. Interactive Parallax

**Technology**: Mouse Events + CSS Transforms

**Description**: 3D logo transformation based on mouse position.

**Implementation**:
```javascript
document.addEventListener('mousemove', (e) => {
    const moveX = (e.clientX / window.innerWidth - 0.5) * 8;
    const moveY = (e.clientY / window.innerHeight - 0.5) * 8;
    
    logo.parentElement.style.transform = 
        `translate(${moveX * -0.2}px, ${moveY * -0.2}px) ` +
        `rotateX(${moveY * 0.1}deg) rotateY(${moveX * -0.1}deg)`;
});
```

### 10. Typewriter Terminal

**Technology**: Vanilla JavaScript + setTimeout

**Description**: Simulated command-line interface with typing effect.

**Implementation**:
```javascript
function typeHead() {
    if (headIdx < headText.length) {
        headEl.textContent += headText.charAt(headIdx);
        headIdx++;
        setTimeout(typeHead, 80);
    } else {
        setTimeout(() => { 
            headEl.textContent = ""; 
            headIdx = 0; 
            typeHead(); 
        }, 8000);
    }
}
```

## 🎨 Color Palette

| Color | Hex | Usage |
|-------|-----|-------|
| Neon Cyan | `#00f2ff` | Primary accents, nodes |
| Neon Pink | `#ff00ff` | Secondary accents, packets |
| Neon Green | `#39ff14` | Status indicators |
| DEDSEC Red | `#ff0033` | Logo, alerts |
| Background | `#020202` | Main background |

## 🏗️ Technology Stack

### Core Technologies
- **HTML5** - Semantic structure
- **CSS3** - Styling and animations
- **Vanilla JavaScript** - Logic and interactivity

### Animation Libraries
- **Anime.js** - Advanced timeline animations
- **CSS Keyframes** - Simple repetitive animations

### Third-Party Services
- **Tailwind CSS** (CDN) - Utility classes
- **Google Fonts** - IBM Plex Mono typography

### Deployment
- **Vercel** - Static hosting platform
- **Custom Configuration** - SSR caching prevention

## ⚡ Performance Optimizations

### 1. Animation Efficiency
- RequestAnimationFrame via Anime.js
- Optimized easing functions
- Minimal DOM manipulation

### 2. Memory Management
- Proper cleanup of timeouts
- Element removal after animation
- Array length reset

### 3. Rendering Performance
- `pointer-events: none` on decorative elements
- Hardware-accelerated transforms
- Efficient CSS filters

### 4. Vercel Optimization
- Static file serving
- SSR caching prevention
- Multiple initialization triggers

## 🎯 Browser Support

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## 🚀 Deployment

### Vercel (Recommended)

This project is already deployed on Vercel:

**Live URL**: https://animated-bg-watchdog.vercel.app/

**GitHub Repository**: https://github.com/praveensaummya

### Manual Deployment

1. Clone repository
```bash
git clone https://github.com/praveensaummya/animated-bg.git
cd animated-bg
```

2. Upload files to static host
3. Configure custom domain (optional)
4. Deploy!

## 🔧 Configuration

### Vercel Configuration (`vercel.json`)
```json
{
  "version": 2,
  "builds": [{
    "src": "index.html",
    "use": "@vercel/static"
  }],
  "routes": [{
    "src": "/(.*)",
    "dest": "/index.html"
  }]
}
```

### Animation Customization

Edit `index.html` to customize:
- Cluster patterns (line 351-356)
- Animation speeds (line 412-414)
- Color palette (lines 12-18)
- Timing intervals (line 449-450)

## 📐 Z-Index Architecture

```
50  - Footer, Firewall Status (top layer)
20  - Header (above logo)
10  - Logo Foreground (main focus)
0   - Network Nodes (background)
```

## 🔍 Debug Mode

Add `?debug=true` to URL to enable debug overlay:

```javascript
if (new URLSearchParams(window.location.search).get('debug')) {
    // Enable debug features
}
```

## 📄 License

MIT License - see LICENSE file for details

## 🤝 Contributing

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Open Pull Request

## 📞 Support

For issues and questions:
- Open GitHub Issue
- Check existing documentation
- Review FIX_SUMMARY.md for Vercel-specific fixes

## 🌟 Acknowledgments

- Anime.js for powerful animation library
- Tailwind CSS for utility framework
- Cyberpunk aesthetic inspiration
- Open source community

## 📈 Changelog

### v2.0.0 - 2026-05-04
- ✅ Single cluster pattern system
- ✅ Faster animation speeds (40% improvement)
- ✅ Vercel SSR caching fix
- ✅ Enhanced layer structure
- ✅ Optimized performance

### v1.0.0 - Initial Release
- Basic animations
- Multiple cluster patterns
- Core functionality

---

