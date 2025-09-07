# Frontend Platforms

Repaso works on three different platforms - web, mobile, and desktop - all built from the same codebase. This means you get the same great experience no matter how you access Repaso, while each platform takes advantage of what makes it special.

## Web: Next.js 15

Next.js is the foundation for all our platforms, ensuring consistent behavior and code reuse across web, mobile, and desktop.

### What Makes It Great

- **App Router**: Modern React patterns that make everything faster and more efficient
- **Server-Side Rendering**: Better SEO and faster initial page loads
- **TypeScript Throughout**: Type safety across the entire web app
- **Local-First Data**: Your data is always available instantly
- **Optimistic Updates**: Changes appear immediately, even before they're saved

### How It Works

- **PGlite**: Embedded Postgres database that runs right in your browser
- **Electric SQL**: Syncs data in the background without slowing you down
- **Service Worker**: Caches content so you can work offline
- **Code Splitting**: Only loads what you need, when you need it

## Mobile: React Native with Expo

React Native gives you native performance while sharing most of the code with our web version.

### How We Built It

- **Electric SQL**: Runs in React Native's JavaScript thread for fast data access
- **SQLite Database**: Local storage optimized for mobile devices
- **Native Performance**: Smooth interactions that feel natural on mobile
- **Shared Logic**: Same business logic as the web version

### Why You'll Love It

- **Native Feel**: Interactions that feel natural on your phone or tablet
- **Device Features**: Access to camera, notifications, and other mobile features
- **Consistent Experience**: Same features as the web version
- **Easy Updates**: Automatic updates through Expo's build system

## Desktop: Electron

Electron gives you full desktop functionality while reusing our web technologies.

### How It's Built

- **Electric SQL**: Runs in Electron's main process for optimal performance
- **SQLite Database**: Local storage that works great on desktop
- **Renderer Process**: Handles the UI through efficient communication
- **File System Access**: Full access to your computer's files

### What You Get

- **Desktop Integration**: Works like a native desktop app
- **File System Access**: Import and export files directly
- **Consistent Experience**: Same great experience as the web version
- **Offline First**: Works completely offline when you need it
- **Easy Distribution**: Install through standard desktop channels

## Shared Code Strategy

### Business Logic

All platforms share the same business logic, so your flashcards, study algorithms, and data processing work exactly the same way everywhere. This means you can start studying on your phone and continue on your computer without missing a beat.

### UI Components

We share React components between web and desktop, and use React Native components for mobile. This maximizes code reuse while making sure each platform feels natural and appropriate.

### Data Layer

Electric SQL provides the same data access patterns across all platforms, with platform-specific storage implementations handled transparently. You don't need to think about it - it just works.

## Platform-Specific Features

### Web Platform

- **Keyboard and Mouse**: Optimized for traditional computer interactions
- **Browser APIs**: Full access to web browser capabilities
- **SEO Friendly**: Search engines can index your content
- **Progressive Web App**: Can be installed like a native app

### Mobile Platform

- **Touch Optimized**: Interfaces designed for touch interaction
- **Smooth Scrolling**: Native performance for smooth scrolling
- **Device Features**: Camera, notifications, and other mobile capabilities
- **App Store**: Easy installation through app stores

### Desktop Platform

- **File System**: Direct access to your computer's files
- **Keyboard Shortcuts**: Power user features for efficiency
- **Window Management**: Full desktop window controls
- **System Integration**: Works with your operating system
