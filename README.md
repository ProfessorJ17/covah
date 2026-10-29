# Havoc v1.0.0

**Post-Quantum encrypted real-time communication platform**

🌐 **Live Site:** https://www.havoc.my.id
👤 **Author:** Professor J
📦 **Version:** 1.0.0

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Configuration](#configuration)
- [Security](#security)
- [Post-Quantum Considerations](#post-quantum-considerations)
- [Architecture](#architecture)
- [Data Models](#data-models)
- [API & Integrations](#api--integrations)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Overview

Havoc is a modern real-time communication platform built with Firebase, enhanced with a post-quantum security layer for message encryption. It provides a complete communication experience including servers, channels, direct messages, voice chat, rich media sharing, and comprehensive user profiles.

### Key Highlights

- **Firebase-powered** - Real-time synchronization using Firebase Firestore
- **Post-quantum encryption layer** - AES-256-GCM encryption for sensitive data
- **Single-file architecture** - Everything in one HTML file for easy deployment
- **Real-time messaging** - Instant message delivery with Firebase listeners
- **Rich user profiles** - Custom avatars, banners, name styles, and identity tags
- **Voice chat** - WebRTC-based voice communication with screen sharing
- **Rich media** - GIFs, images, audio clips, and reactions
- **Rich messaging features** - Threads, pins, replies, mentions, and role-based permissions
- **End-to-end encryption** - Messages encrypted before storage, decrypted on client

---

## ✨ Features

### 🏠 Server Management
- **Server Creation** - Create servers with custom names, descriptions, icons, and banners
- **Server Settings** - Configure public/private discovery, custom tags (2-4 characters), tag emojis, and tag colors
- **Channel Management** - Create text and voice channels
- **Role System** - Custom roles with colors and permissions
- **Member Management** - Invite users, kick members, view member list with status
- **Server Tag Uniqueness** - Global tag reservation system prevents duplicate server tags

### 💬 Messaging
- **Real-time Chat** - Instant message delivery with Firestore
- **Message Replies** - Reply to messages with context
- **Message Reactions** - Add emoji reactions to messages
- **Message Pinning** - Pin important messages for easy access
- **Mentions** - @everyone, @here, and @role mentions with notification suppression
- **Rich Content** - Send images, GIFs, and audio clips
- **Threads** - Create threaded discussions within channels
- **Message History** - Scrollable message feed with timestamps

### 👥 User Profiles
- **Custom Avatars** - Generated avatars (DiceBear) or custom images/GIFs
- **Custom Banners** - Color gradients or custom images/GIFs
- **Name Styling** - Custom fonts, colors, and gradients for usernames
- **Identity Tags** - Server-specific tags that display next to your name
- **Status Indicators** - Online, Idle, Do Not Disturb, Invisible, Offline
- **User Notes** - Add private notes about other users
- **Account Dates** - Display account creation and server join dates
- **Profile Persistence** - All profile settings sync across devices

### 👥 Social Features
- **Friends System** - Send, accept, and manage friend requests
- **Direct Messages** - Private conversations with friends
- **User Blocking** - Block users to prevent unwanted contact
- **User Context Menu** - Quick actions for messaging, friending, blocking
- **Presence System** - Real-time online/offline status across the app

### 🎤 Voice Chat
- **Voice Channels** - Join voice channels for group conversations
- **Screen Sharing** - Share your screen with voice channel participants
- **Audio Recording** - Record and send audio clips up to 30 seconds
- **Voice Activity Detection** - Visual indicators for speaking participants
- **Audio Device Selection** - Choose specific microphone and speaker devices

### 🎨 Customization
- **Avatar Cropping** - Crop and zoom avatars with circular masking
- **Banner Customization** - Choose from preset gradients or custom colors
- **GIF Integration** - Search and select GIFs from Giphy
- **Name Styling** - 5 custom fonts, 8 color gradients, custom gradient builder
- **Theme** - Dark theme optimized for comfort

### 🔔 Notifications
- **Mention Notifications** - Get notified when mentioned
- **Sound Effects** - Notification sounds (Web Audio API)
- **Notification Modes** - All mentions, @mentions only, or none per channel
- **Suppression** - Suppress @everyone, @here, and @role mentions
- **Mute System** - Mute entire servers or specific channels

### 🔍 Discovery
- **Public Server Discovery** - Browse and join public servers
- **Server Search** - Search servers by tags
- **Server Tags** - 2-4 character unique identifiers for servers
- **Server Cards** - Preview servers with member counts and descriptions

### 🛡️ Security & Privacy
- **Firebase Authentication** - Email/password and anonymous login
- **Password Reset** - Secure password reset via email
- **Remember Me** - Persistent login with encryption
- **Session Management** - Secure sign-out and session cleanup
- **Data Persistence** - All settings sync to Firestore

### 📱 Mobile & Accessibility
- **Responsive Design** - Works on desktop and mobile
- **Touch-Friendly** - Optimized for touch interactions
- **Keyboard Shortcuts** - Escape to close modals
- **Focus Management** - Proper focus handling for accessibility

---

## 🛠️ Technology Stack

### Frontend
- **HTML5** - Single-file architecture
- **Tailwind CSS** - Utility-first CSS framework (via CDN)
- **Font Awesome 6.5.1** - Icon library
- **Vanilla JavaScript** - No framework dependencies

### Backend
- **Firebase Authentication** - User authentication (email/password, anonymous)
- **Firebase Firestore** - Real-time database for all data storage
- **Firebase Storage** - File storage for media (optional)

### Security Layer
- **Web Crypto API** - Browser-native cryptographic operations
- **AES-256-GCM** - Encryption for messages and sensitive data
- **HMAC-SHA256** - Digital signatures for message integrity
- **Post-quantum ready** - Architecture designed to upgrade to post-quantum algorithms when available

### APIs & Services
- **Giphy API** - GIF search and selection
- **DiceBear API** - Avatar generation
- **WebRTC** - Voice chat and screen sharing
- **Web Audio API** - Sound effects and audio recording

### Development Tools
- **ES6+ JavaScript** - Modern JavaScript features
- **Async/Await** - Promise-based asynchronous operations
- **LocalStorage** - Client-side preferences persistence

---

## 📦 Installation

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Firebase project with Authentication and Firestore enabled
- Giphy API key (optional, for GIF features)

### Setup Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/ProfessorJ17/covah.git
   cd covah
   ```

2. **Configure Firebase**
   - Create a Firebase project at https://console.firebase.google.com
   - Enable Authentication (Email/Password and Anonymous)
   - Enable Firestore Database
   - Get your Firebase configuration

3. **Update Firebase Configuration**
   - Open `index.html`
   - Locate the Firebase initialization section (around line 1096)
   - Replace the placeholder config with your Firebase credentials:
   ```javascript
   const app = initializeApp({
     apiKey: "YOUR_API_KEY",
     authDomain: "YOUR_PROJECT.firebaseapp.com",
     projectId: "YOUR_PROJECT_ID",
     storageBucket: "YOUR_PROJECT.appspot.com",
     messagingSenderId: "YOUR_SENDER_ID",
     appId: "YOUR_APP_ID"
   });
   ```

4. **Configure Giphy API (Optional)**
   - Get a Giphy API key from https://developers.giphy.com
   - Update the `GIPHY_API_KEY` constant in `index.html`

5. **Deploy**
   - **Option 1: Static Hosting**
     - Upload `index.html` to any static hosting service (Netlify, Vercel, GitHub Pages)
   - **Option 2: Firebase Hosting**
     ```bash
     npm install -g firebase-tools
     firebase login
     firebase init hosting
     firebase deploy
     ```
   - **Option 3: Traditional Web Server**
     - Place `index.html` in your web server's public directory

---

## ⚙️ Configuration

### Firebase Security Rules

Add these rules to your Firestore security rules:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Users collection
    match /users/{userId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null && request.auth.uid == userId;
      
      // Friend requests
      match /friendRequests/{requestId} {
        allow read: if request.auth != null;
        allow write: if request.auth != null && 
                     (request.auth.uid == userId || resource.data.fromUid == request.auth.uid);
      }
      
      // Friends
      match /friends/{friendId} {
        allow read: if request.auth != null;
        allow write: if request.auth != null && request.auth.uid == userId;
      }
      
      // Notes
      match /notes/{noteId} {
        allow read, write: if request.auth != null && request.auth.uid == userId;
      }
    }
    
    // Servers collection
    match /servers/{serverId} {
      allow read: if true; // Public read for discovery
      allow create: if request.auth != null;
      allow update: if request.auth != null && 
                    (request.auth.uid == resource.data.ownerUid || 
                     get(/databases/$(database)/documents/servers/$(serverId)/members/$(request.auth.uid)).data.role == 'admin');
      allow delete: if request.auth != null && request.auth.uid == resource.data.ownerUid;
      
      // Server members
      match /members/{memberId} {
        allow read: if request.auth != null;
        allow write: if request.auth != null && 
                     (request.auth.uid == resource.data.ownerUid ||
                      request.auth.uid == memberId);
      }
      
      // Channels
      match /channels/{channelId} {
        allow read: if request.auth != null;
        allow write: if request.auth != null && 
                     get(/databases/$(database)/documents/servers/$(serverId)/members/$(request.auth.uid)).data.role in ['owner', 'admin'];
      }
      
      // Messages
      match /channels/{channelId}/messages/{messageId} {
        allow read: if request.auth != null;
        allow create: if request.auth != null;
        allow delete: if request.auth != null && 
                      (request.auth.uid == resource.data.uid ||
                       get(/databases/$(database)/documents/servers/$(serverId)/members/$(request.auth.uid)).data.role in ['owner', 'admin']);
      }
      
      // Pins
      match /channels/{channelId}/pins/{pinId} {
        allow read: if request.auth != null;
        allow write: if request.auth != null;
      }
      
      // Threads
      match /channels/{channelId}/threads/{threadId} {
        allow read: if request.auth != null;
        allow create: if request.auth != null;
      }
      
      // Roles
      match /roles/{roleId} {
        allow read: if request.auth != null;
        allow write: if request.auth != null && 
                     get(/databases/$(database)/documents/servers/$(serverId)/members/$(request.auth.uid)).data.role in ['owner', 'admin'];
      }
    }
    
    // Server tags (for uniqueness)
    match /serverTags/{tag} {
      allow read: if true;
      allow create: if request.auth != null;
      allow delete: if request.auth != null && resource.data.ownerUid == request.auth.uid;
    }
    
    // Usernames (for uniqueness)
    match /usernames/{username} {
      allow read: if true;
      allow create: if request.auth != null;
      allow delete: if request.auth != null && resource.data.uid == request.auth.uid;
    }
  }
}
```

### Environment Variables

The application uses client-side configuration. Sensitive values should be:

1. **Firebase Config** - Add to `index.html` (acceptable for client-side Firebase)
2. **Giphy API Key** - Add to `index.html` (rate-limited public API)
3. **Local Storage** - Stores user preferences locally (mutes, settings, etc.)

### Customization Options

Edit the following constants in `index.html`:

- `PROFILE_FONTS` - Available fonts for name styling
- `NAME_GRADIENTS` - Available color gradients for names
- `HAVOC_DOMAIN` - Set to `https://www.havoc.my.id`
- `GIPHY_API_KEY` - Your Giphy API key

---

## 🔒 Security

### Authentication Security
- **Firebase Authentication** - Industry-standard authentication
- **Password Hashing** - Firebase handles password hashing with bcrypt
- **Session Management** - Firebase manages secure sessions
- **Password Reset** - Secure email-based password reset
- **Anonymous Users** - Temporary anonymous accounts for testing

### Post-Quantum Security Layer
- **AES-256-GCM Encryption** - Messages encrypted before Firebase storage
- **HMAC-SHA256 Signatures** - Message integrity verification
- **Session-based Keys** - Keys cleared on logout
- **Transparent Decryption** - Automatic decryption on client
- **Quantum-Resistant** - Resists Grover's algorithm

### Data Security
- **Firestore Security Rules** - Role-based access control
- **Client-Side Validation** - Input validation on all forms
- **XSS Prevention** - HTML escaping with `esc()` function
- **CSRF Protection** - Firebase handles CSRF tokens
- **Content Security Policy** - Recommended for production deployment

### Privacy Features
- **User Notes** - Private notes encrypted and stored in Firebase
- **Blocking** - Block users to prevent unwanted contact
- **Invisible Status** - Hide online status
- **Private Servers** - Servers can be private (not discoverable)
- **DM Privacy** - Direct messages encrypted with session keys

### Best Practices
1. **Never commit secrets** - Firebase config is safe
2. **Use HTTPS** - Always deploy with HTTPS
3. **Rate Limiting** - Firebase provides built-in rate limiting
4. **Audit Logs** - Firebase provides audit logging
5. **Regular Updates** - Keep Firebase SDKs updated

---

## 🔐 Post-Quantum Security Implementation

### Current Implementation (v1.0.0)

Havoc v1.0.0 implements a post-quantum-ready encryption layer using Web Crypto API:

#### Encryption (AES-256-GCM)
- **Algorithm**: AES-256-GCM (Galois/Counter Mode)
- **Key Size**: 256 bits
- **IV Size**: 96 bits (12 bytes)
- **Quantum Resistance**: Resistant to Grover's algorithm (requires 2^128 operations vs 2^256 for classical brute force)
- **Implementation**: Web Crypto API (browser-native)

#### Digital Signatures (HMAC-SHA256)
- **Algorithm**: HMAC-SHA256
- **Purpose**: Message integrity and authentication
- **Implementation**: Web Crypto API

### Security Features

1. **Transparent Encryption** - Messages encrypted before Firebase storage
2. **Automatic Decryption** - Decrypted automatically on client side
3. **Key Management** - Session-based keys, cleared on logout
4. **Signature Verification** - All messages signed for integrity
5. **Fallback Support** - Graceful fallback if encryption fails

### Implementation Details

#### Message Encryption Flow
```javascript
// 1. Generate session key
const keyId = await PQ.generateKey();

// 2. Encrypt message content
const encrypted = await PQ.encrypt(messageContent, keyId);

// 3. Sign message
const signature = await PQ.sign({
  uid: user.uid,
  content: encrypted,
  ts: Date.now()
});

// 4. Store in Firebase
await PQFirestore.secureAddDoc(collectionRef, {
  content: encrypted,
  signature: signature,
  _pq: { encrypted: true, algorithm: 'AES-256-GCM' }
});
```

#### Decryption Flow
```javascript
// 1. Fetch from Firebase
const doc = await getDoc(docRef);
const data = doc.data();

// 2. Decrypt automatically
const decrypted = await PQFirestore.decryptData(data);

// 3. Verify signature
const valid = await PQ.verify(decrypted, data.signature);
```

### Security Parameters

| Parameter | Value | Notes |
|-----------|-------|-------|
| Encryption Algorithm | AES-256-GCM | Web Crypto API native |
| Key Size | 256 bits | Industry standard |
| IV Size | 96 bits | GCM specification |
| Signature Algorithm | HMAC-SHA256 | Web Crypto API |
| Key Lifetime | Session-based | Cleared on logout |
| Encryption Scope | Messages, bio, status, notes | Sensitive fields only |

### Future Post-Quantum Migration

**Phase 1: Enhanced Security (v1.1.0+)**
- Add hybrid encryption (AES-256 + PQ algorithm)
- Implement post-quantum algorithms when browser support available
- Add post-quantum signatures

**Phase 2: Full Post-Quantum (v2.0.0+)**
- Complete migration to post-quantum algorithms
- Remove classical algorithm dependencies
- Full audit of cryptographic implementation

### Post-Quantum Resources
- [NIST Post-Quantum Cryptography Standardization](https://csrc.nist.gov/projects/post-quantum-cryptography)
- [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API)
- [Google's Post-Quantum Cryptography Initiative](https://security.googleblog.com/)

---

## 🏗️ Architecture

### Firebase-Based Architecture
Havoc uses Firebase for reliable data storage with a post-quantum encryption layer:

```
User Action → JavaScript → Post-Quantum Encryption → Firebase Firestore → Real-time Sync → Decryption → UI Update
```

### Key Components

1. **Firebase Layer**
   - Firebase Authentication for user authentication
   - Firebase Firestore for real-time data storage
   - Firebase Storage for media files
   - Real-time listeners for instant updates

2. **Post-Quantum Security Layer**
   - Web Crypto API for cryptographic operations
   - AES-256-GCM encryption for sensitive data
   - HMAC-SHA256 signatures for message integrity
   - Transparent encryption/decryption
   - Session-based key management

3. **State Management (`S` object)**
   - Global state object
   - Holds user profile, server data, channels, messages
   - Updates trigger UI re-renders

4. **Profile Cache (`S.profileCache`)**
   - Caches user profiles for performance
   - Includes status, style, avatar, etc.
   - TTL-based expiration

5. **Members Cache (`S.membersCache`)**
   - Caches server member data
   - Includes roles, join dates, permissions

6. **Message Listeners**
   - Real-time Firestore listeners
   - Auto-update on new messages
   - Cleanup on server/channel switch

7. **Heartbeat System**
   - Periodic presence updates
   - Last-seen timestamp
   - Status propagation

### Single-File Architecture
Havoc uses a single HTML file containing:
- HTML structure
- CSS styles (Tailwind + custom)
- JavaScript logic
- Firebase SDK integration
- Post-quantum cryptography layer

### Firebase Collections

| Collection | Purpose | Key Fields |
|------------|---------|------------|
| `users/{uid}` | User profiles | handle, avatar, bio, status, style, userTag, signature |
| `usernames/{handle}` | Username uniqueness | uid, handle, updatedAt |
| `servers/{serverId}` | Server data | name, desc, iconUrl, bannerUrl, isPublic, tag, tags |
| `serverTags/{tag}` | Server tag uniqueness | serverId, ownerUid |
| `servers/{serverId}/members/{uid}` | Server membership | role, joinedAt |
| `servers/{serverId}/channels/{channelId}` | Channel data | name, type, createdAt |
| `servers/{serverId}/channels/{channelId}/messages/{messageId}` | Messages | content, uid, handle, ts, replyTo, reactions, signature |
| `servers/{serverId}/channels/{channelId}/pins/{messageId}` | Pinned messages | content, handle, pinnedBy, pinnedAt |
| `servers/{serverId}/channels/{channelId}/threads/{threadId}` | Threads | name, createdBy, createdAt |
| `servers/{serverId}/roles/{roleId}` | Roles | name, color, permissions |
| `users/{uid}/friends/{friendUid}` | Friend relationships | handle, avatar, addedAt |
| `users/{uid}/friendRequests/{requestId}` | Friend requests | handle, avatar, ts |
| `users/{uid}/outgoingRequests/{toUid}` | Outgoing requests | handle, avatar, ts |
| `users/{uid}/notes/{uid}` | User notes | text, updatedAt |
| `dms/{dmId}/messages/{messageId}` | DM messages | from, content, ts, signature |

### Data Flow Example

**Sending a Message:**
1. User types message in chat
2. Client encrypts message with post-quantum layer (AES-256-GCM)
3. Client signs message with HMAC-SHA256
4. Encrypted data sent to Firebase Firestore
5. Real-time listener detects new message
6. Client decrypts message automatically
7. UI updates with decrypted content

**Joining a Server:**
1. User clicks server in sidebar
2. Query Firestore for server data
3. Load channels from Firestore
4. Subscribe to Firestore real-time listeners
5. Load messages from Firestore
6. Decrypt encrypted messages automatically
7. UI renders server view

---

## 📊 Data Models

### User Profile (Firebase Document)
```javascript
{
  uid: string,           // Firebase Auth UID
  email: string,         // User email
  handle: string,         // Unique username
  avatar: string,        // Avatar URL or seed
  bio: string,           // User bio (encrypted)
  status: string,        // online | idle | dnd | invisible
  lastSeen: number,      // Timestamp
  createdAt: number,     // Account creation timestamp
  style: {
    font: string,        // Custom font
    nameColor: string,   // Custom color
    nameGradient: string,// Gradient preset
    customGradient: string,// Custom gradient
    banner: {            // Banner config
      type: 'color' | 'gif' | 'gradient',
      value: string
    },
    avatarCrop: {        // Avatar crop settings
      zoom: number,
      x: number,
      y: number
    }
  },
  userTag: string,       // Selected identity tag
  signature: string      // HMAC-SHA256 signature
}
```

### Server (Firebase Document)
```javascript
{
  id: string,            // Server ID
  name: string,          // Server name
  desc: string,          // Server description
  ownerUid: string,      // Owner's UID
  iconUrl: string,       // Server icon URL
  bannerUrl: string,     // Server banner URL
  isPublic: boolean,     // Public discovery flag
  tag: string,           // 2-4 character tag
  tagEmoji: string,      // Tag emoji
  tagBgColor: string,    // Tag background color
  tagEmojiColor: string, // Tag emoji color
  tags: string[],        // Search tags
  memberCount: number,   // Member count
  createdAt: number      // Creation timestamp
}
```

### Message (Firebase Document)
```javascript
{
  id: string,            // Message ID
  content: string,       // Encrypted message content
  uid: string,           // Author UID
  handle: string,        // Author handle
  avatar: string,        // Author avatar
  ts: number,            // Timestamp
  imageUrl: string,      // Optional image URL
  audioUrl: string,      // Optional audio URL
  replyTo: string,       // Reply to message ID
  replyHandle: string,   // Reply to handle
  reactions: {           // Reactions
    [emoji]: [uid1, uid2, ...]
  },
  signature: string      // HMAC-SHA256 signature
}
```

---

## 🔌 API & Integrations

### Firebase SDKs Used
- Firebase App
- Firebase Authentication
- Firebase Firestore
- Firebase Storage (optional)

### Security Layer
- Web Crypto API (browser-native)
- AES-256-GCM encryption
- HMAC-SHA256 signatures

### External APIs
- **Giphy API** - GIF search and selection
  - Endpoint: `https://api.giphy.com/v1/gifs/search`
  - Rate limiting: Configurable
  - Fallback: Local GIF dataset

- **DiceBear API** - Avatar generation
  - Endpoint: `https://api.dicebear.com/7.x/bottts/svg`
  - No authentication required
  - Highly available

### WebRTC
- Peer-to-peer voice chat
- Screen sharing
- STUN/TURN servers (custom network)

### Web Audio API
- Notification sounds
- Audio recording
- Audio playback

---

## 🤝 Contributing

### Development Setup
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Code Style
- Use 2-space indentation
- Follow existing naming conventions
- Add comments for complex logic
- Test all features before submitting

### Feature Requests
- Open an issue with the "enhancement" label
- Describe the feature in detail
- Provide use cases
- Consider security implications

### Bug Reports
- Open an issue with the "bug" label
- Provide steps to reproduce
- Include browser and OS information
- Add screenshots if applicable

---

## 📝 Version History

### v1.0.0 (October 28, 2026)
- Initial release
- Firebase-based real-time communication
- Post-quantum security layer (AES-256-GCM encryption)
- Message encryption and digital signatures
- Complete feature set for real-time communication
- Voice chat with screen sharing
- Rich media support
- User profiles with customization
- Server management
- Friends and DMs
- Public discovery
- End-to-end encryption for messages
- Typing indicators for real-time communication

---

## 📄 License

This project is proprietary software. All rights reserved.

**Copyright © 2026 Professor J**

For licensing inquiries, contact: [contact@havoc.my.id](mailto:contact@havoc.my.id)

---

## 🙏 Acknowledgments

- **Firebase** - Backend infrastructure
- **Tailwind CSS** - Utility-first CSS framework
- **Font Awesome** - Icon library
- **Giphy** - GIF API
- **DiceBear** - Avatar generation
- **Modern chat platforms** - Inspiration for UI/UX design

---

## 📞 Support

- **Website:** https://www.havoc.my.id
- **Email:** admin@j10.33mail.com

---

**Built with ❤️ by Professor J**

*Last updated: October 29, 2026*
