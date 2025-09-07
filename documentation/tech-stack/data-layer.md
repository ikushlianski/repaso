# Data Layer

Our data layer ensures your information is always available, fast, and secure across all platforms. We handle all the complex stuff so you can focus on learning.

## Neon Postgres

Neon provides our main database - the single source of truth for all your data. Electric SQL then syncs this data to all your devices automatically.

### What Makes It Great

- **EU Data Residency**: Your data stays in Europe for compliance and privacy
- **Electric SQL Ready**: Built-in support for our sync technology
- **Auto-Scaling**: Automatically adjusts to handle more users without us doing anything
- **Data Safety**: Point-in-time recovery means your data is always safe
- **Development Branches**: We can test new features without affecting your data

### Pricing That Makes Sense

- **Generous Free Tier**: Perfect for development and getting started
- **Pay-As-You-Scale**: Only pay for what you use
- **No Upfront Costs**: No commitments or hidden fees
- **Transparent Pricing**: Clear costs based on actual usage

## Local Storage

Each platform uses local storage for instant access and offline functionality. This is what makes everything feel so fast.

### How It Works on Each Platform

**Web**: PGlite (embedded Postgres in browser)
- **Full SQL Compatibility**: All the power of Postgres in your browser
- **Runs in Browser**: No server required, everything happens locally
- **Automatic Persistence**: Your data is saved automatically
- **No Server Needed**: Works completely offline

**Mobile**: SQLite (native database)
- **Mobile Optimized**: Built for mobile performance
- **Minimal Memory**: Uses very little of your phone's memory
- **Native Integration**: Works seamlessly with your device
- **Reliable Storage**: Your data is always safe

**Desktop**: SQLite (via Electron)
- **Desktop Integration**: Full access to your computer's capabilities
- **File System Access**: Can work with your computer's files
- **Native Performance**: Fast and responsive
- **Cross-Platform**: Works on Windows, Mac, and Linux

## File Storage

For media files and document uploads, we use object storage solutions that are fast, reliable, and cost-effective.

### Our Storage Options

**Vercel Blob**: Simple integration with Next.js, great for getting started
**AWS S3**: More features and control, but higher complexity
**Cloudflare R2**: Good balance of features and cost

### Our Strategy

- **Start Simple**: Begin with Vercel Blob for easy setup
- **Optimize Costs**: Move to Cloudflare R2 for better pricing
- **Scale Up**: Consider AWS S3 if we need advanced features

## Data Synchronization

### Electric SQL Integration

Electric SQL handles all the complex synchronization for us:
- **Incremental Sync**: Only sends data that has changed
- **Background Processing**: Syncs without slowing you down
- **Compression**: Efficient data transfer to save bandwidth
- **Smart Batching**: Groups changes together for efficiency

### Conflict Resolution

When you make changes on multiple devices, Electric SQL automatically handles conflicts:
- **Simple Conflicts**: Last-write-wins for straightforward cases
- **Complex Conflicts**: Custom logic for more complicated situations
- **User Notification**: We'll let you know if manual resolution is needed

### Offline Support

- **Full Offline**: Work completely offline with all your data
- **Automatic Sync**: When you're back online, everything syncs automatically
- **No Data Loss**: Conflicts are resolved without losing any information
- **Progress Indicators**: See sync status and progress

## Data Security

### Encryption

- **AES-256 Encryption**: Your data is encrypted at rest with military-grade encryption
- **TLS 1.3**: All data in transit is encrypted with the latest security standards
- **End-to-End Encryption**: Sensitive data is encrypted from your device to ours
- **Secure Key Management**: Encryption keys are managed by secure providers

### Access Control

- **User Isolation**: Your data is completely separate from other users
- **Role-Based Permissions**: Different access levels for different features
- **API Authentication**: All API access is authenticated and authorized
- **Audit Logging**: We log sensitive operations for security monitoring

### Compliance

- **GDPR Compliance**: Full compliance with European data protection laws
- **Right to be Forgotten**: You can delete your data completely
- **Data Export**: You can export all your data whenever you want
- **Privacy by Design**: Privacy is built into everything we do
