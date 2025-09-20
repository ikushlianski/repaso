# Core Architecture

The foundation of Repaso is built around making your data instantly available everywhere, while keeping everything synchronized seamlessly in the background.

## Local-First Sync: Electric SQL

Electric SQL solves the tricky problem of keeping your data synchronized across all your devices. Instead of building custom sync logic, we use Electric SQL to handle all the complexity while giving you instant responses and true offline functionality.

### How It Works

Electric SQL takes data from our main database and syncs it to your local device. It only sends the data you actually need, manages your connection automatically, and handles conflicts when you make changes on multiple devices. The best part? It works the same way across all platforms.

### Why This Matters

- **Instant Everything**: Your data is always local, so everything happens instantly
- **True Offline**: Work completely offline, then sync when you're back online
- **No Conflicts**: Automatically resolves conflicts when you edit on multiple devices
- **Scales Forever**: Works just as well with millions of users as it does with hundreds

## Database: Neon Postgres

Neon gives us a managed Postgres database that's perfect for our needs. It's based in the EU for compliance, scales automatically, and handles all the complex database management for us.

### Why We Chose Neon

- **EU Data Residency**: Your data stays in Europe for compliance and privacy
- **Serverless Scaling**: Automatically adjusts to handle more users without us doing anything
- **Electric SQL Ready**: Built-in support for the sync technology we use
- **Generous Free Tier**: Perfect for development and getting started
- **No DevOps Required**: We focus on building features, not managing databases

### What You Get

- **Data Safety**: Point-in-time recovery means your data is always safe
- **Development Branches**: We can test new features without affecting your data
- **Smart Scaling**: Automatically adjusts based on how much you're using it
- **Built-in Monitoring**: We can see how everything is performing and fix issues before they affect you

## Backend: Simple APIs or Advanced Frameworks

We keep our APIs simple and focused. Most of the heavy lifting is done by Electric SQL, so our APIs just handle the essential operations like creating flashcards and recording your progress.

### What Our APIs Do

- **User Management**: Sign in, sign out, and manage your account
- **Content Creation**: Create and update your flashcards
- **Progress Tracking**: Record how you're doing with your studies
- **File Handling**: Upload documents and images
- **Settings**: Manage your preferences and configuration

### Our Design Philosophy

- **Keep It Simple**: APIs should be straightforward and easy to understand
- **Let Electric SQL Work**: We handle reads locally, APIs handle writes
- **Type Safety**: Everything is written in TypeScript to catch errors early
- **Proper Error Handling**: Clear error messages and graceful failure handling

### When We Need More Power

For complex AI processing and advanced features, we can use dedicated backend frameworks:

**Next.js API Routes**: Perfect for getting started and simple operations
- Built-in TypeScript support
- Seamless integration with our frontend
- Great for basic CRUD operations

**Dedicated Backend Frameworks**: For complex AI processing and advanced features
- **Fastify**: High-performance with great validation
- **Adonis**: Full-featured with built-in tools
- **Express**: Mature ecosystem with lots of plugins
- **Hono**: Lightweight and edge-optimized

### Choosing the Right Tool

- **Next.js API Routes**: When we're starting out or need simple operations
- **Dedicated Backend**: When we need AI processing, complex logic, or high performance

## How Data Flows

Here's how your data moves through our system:

**Main Database** → **Sync Engine** → **Your Device** → **Instant Access**

### When You Make Changes

Your changes go through our API to the main database, then Electric SQL automatically syncs them to all your other devices in the background.

### When You Read Data

Everything comes from your local device for instant response. Electric SQL keeps everything fresh in the background without slowing you down.

### When You're Offline

You can work completely offline, and when you're back online, everything syncs automatically. Electric SQL handles all the complexity of making sure your data is consistent across all devices.
