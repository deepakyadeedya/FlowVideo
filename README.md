📱 FlorFeed – Vertical Video Feed App
FlorFeed is a lightweight SwiftUI prototype that mimics a TikTok/Reels-style infinite vertical video feed. The app fetches a list of HLS video URLs from a manifest endpoint, renders each video full-screen, and loops playback automatically as the user swipes between items.
✨ Features
Swift + SwiftUI: Built natively with SwiftUI for clarity and modern declarative UI.
Remote manifest loading: Downloads a JSON manifest of video URLs at launch.
Full-screen playback: Each video fills the device screen and ignores safe areas.
Seamless looping: Videos restart automatically when they reach the end.
Vertical paging: Users swipe vertically between videos with smooth paging behavior.
Lifecycle aware: Playback starts when a video appears and pauses when it disappears, preventing resource leaks.
🛠️ Architecture
VideoStore (ObservableObject)
Responsible for fetching and decoding the manifest JSON.
Publishes a list of URL items for the UI layer.
VideoPlayerView
Wraps AVPlayer inside SwiftUI’s VideoPlayer.
Handles auto-play, loop via AVPlayerItemDidPlayToEndTime, and cleanup on disappear.
FeedView
Displays videos in a vertical TabView (iOS 16 rotation trick or iOS 17’s .scrollTargetBehavior(.paging)).
Provides the immersive “swipe to next” feed experience.
📦 Dependencies
Swift 5.9+
iOS 16+ (rotation trick for vertical paging)
iOS 17+ (native vertical paging via scrollTargetBehavior)
No external libraries are required — only SwiftUI and AVKit.
