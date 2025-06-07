# Comrades Ultra Marathon Personal Race Tracker
## Product Requirements Document (PRD)

### Executive Summary
A mobile-optimized web application designed for support crews to track runners during ultra-marathon events, specifically built for the Comrades Marathon (89km). The app enables real-time progress tracking, pace calculations, and social media updates throughout the race.

### Problem Statement
Support crews need an easy way to:
- Track their runner's progress against planned times
- Calculate updated finish projections based on actual performance
- Share updates with friends and family
- Account for terrain difficulty and race-specific factors
- Work reliably on mobile devices during race day

### Solution Overview
A single-page web application that:
- Visualizes the race route in 500m segments
- Allows tap-to-record timing at any point
- Automatically recalculates projections using weighted recent performance
- Generates shareable updates for social media
- Works offline once loaded
- Persists data locally

## Core Features

### 1. Visual Race Map
- **Segment Display**: 5km sections broken into 500m segments
- **Terrain Visualization**: 
  - Yellow = Flat terrain
  - Red = Uphill sections  
  - Green = Downhill sections
- **Landmarks**: Major points labeled (Big Polly's, Drummond, etc.)
- **Fuel Stations**: Purple heart markers with automatic 1-minute delay
- **Progress Indicator**: Blue highlighting for completed segments

### 2. Time Tracking
- **Tap Interface**: Touch any segment to record time
- **Projected vs Actual**: Shows expected time, allows recording actual
- **Smart Recalculation**: Updates all future projections based on recent pace
- **Weighted Performance**: Recent segments weighted more heavily (70% decay)
- **Difficulty Factors**: Terrain-adjusted calculations (+10% uphill, -10% downhill)

### 3. Settings Configuration
- **Start Time**: Official race gun time
- **Race Distance**: Customizable for different events
- **Target Finish Time**: Set goal time for pace calculations
- **Start Line Delay**: Account for congestion at start

### 4. Social Sharing
- **One-Tap Share**: Generate formatted update messages
- **Smart Status**: Automatically determines if ahead/behind/on track
- **Copy to Clipboard**: Universal compatibility
- **Example Output**: "🏃‍♀️ Rhona has just passed the 40.5km mark at 09:15:30 and is projected to finish at 14:35. She's running faster than planned! 💪"

### 5. Performance Logging
- **Automatic Recording**: Every checkpoint saved with context
- **Delta Tracking**: Shows +/- variance from plan
- **Complete History**: Full race log accessible anytime
- **Export Ready**: JSON format for analysis
- **Persistent Storage**: Survives browser refresh

## Technical Specifications

### Architecture
- **Type**: Single-page application (SPA)
- **Stack**: Pure HTML5, CSS3, JavaScript (ES6+)
- **Dependencies**: None (zero external libraries)
- **Storage**: LocalStorage for persistence
- **Compatibility**: All modern mobile browsers

### Key Algorithms

#### Pace Calculation
```
basePace = (targetTime - startDelay) / distance
segmentTime = 0.5km * basePace * difficultyFactor * terrainModifier
```

#### Weighted Recent Performance
```
weight(n) = 0.7^n (exponential decay)
recentPace = Σ(pace[i] * weight[i]) / Σ(weight[i])
```

### Data Model
```javascript
segment = {
  id: number,
  km: number,
  endKm: number,
  terrain: 'yellow'|'red'|'green',
  difficulty: number,
  landmarks: string,
  fuelStation: boolean
}

logEntry = {
  timestamp: ISO8601,
  km: number,
  actualTime: HH:MM:SS,
  projectedTime: HH:MM:SS,
  delta: ±MM:SS,
  terrain: string,
  pace: seconds/km
}
```

## User Interface

### Mobile-First Design
- **Touch Optimized**: Large tap targets (40px minimum)
- **No Zoom**: Prevented double-tap zoom
- **Fixed Elements**: Header and stats stay visible
- **Responsive**: Adapts to any screen size
- **Offline Ready**: Works without connection

### Visual Design
- **Branding**: Comrades yellow (#FFD700) and black theme
- **Typography**: System fonts for performance
- **Animations**: Subtle feedback on interactions
- **Accessibility**: High contrast, semantic markup

## Use Cases

### Primary Use Case
**Race Day Tracking**
1. Support crew member opens app at race start
2. Sets start time and any delays
3. Taps segments as runner passes timing points
4. App recalculates finish projection
5. Shares updates with supporters
6. Reviews performance post-race

### Secondary Use Cases
- **Pre-Race Planning**: Set target times, review route
- **Training Runs**: Track performance on route sections
- **Post-Race Analysis**: Export and analyze pacing data
- **Other Races**: Configure for different distances

## Future Enhancements

### Potential Features
1. **Multiple Runners**: Track several athletes simultaneously
2. **GPS Integration**: Auto-detect position
3. **Weather Data**: Factor conditions into projections
4. **Historical Comparison**: Compare to previous years
5. **Team Sharing**: Real-time sync between devices
6. **Photo Upload**: Attach images to checkpoints
7. **Advanced Analytics**: Pace bands, split analysis

### Platform Expansion
- Progressive Web App (PWA) with offline support
- Native mobile apps for iOS/Android
- Integration with Strava/Garmin
- WhatsApp Business API for automated updates

## Success Metrics
- Accurate pace predictions (within 2% of actual)
- Zero crashes during 12-hour race day usage
- <3 second load time on 3G connection
- Successful social shares per race
- Battery efficiency (full day usage)

## Technical Debt & Limitations
- No real-time sync between devices
- Manual time entry (no GPS/automatic detection)
- Limited to pre-defined checkpoints
- No backup beyond local device
- English-only interface

## Deployment
- Single HTML file (no build process)
- Host on GitHub Pages (free)
- Share via URL or QR code
- Works immediately, no installation

---

**Version**: 1.0  
**Last Updated**: December 2024  
**Primary Use Case**: Comrades Ultra Marathon 2025  
**Target Users**: Support crews, family, friends of ultra-marathon runners