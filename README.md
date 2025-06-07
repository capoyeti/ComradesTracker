# Comrades Ultra Marathon Personal Race Tracker

A mobile-optimized web application for tracking runner progress during the Comrades Ultra Marathon (89km). Built specifically to help support crews and spectators track their runner's real-time progress and share updates with friends and family.

## 🏃‍♀️ Features

### Real-Time Race Tracking
- **Visual Progress Map**: Color-coded 5km sections showing terrain difficulty
  - 🟡 Yellow = Flat terrain
  - 🔴 Red = Uphill sections
  - 🟢 Green = Downhill sections
  - 💜 Purple hearts = Fuel stations
- **500m Precision**: Track progress in 500m segments for accurate timing
- **Smart Pace Calculation**: Automatically adjusts predictions based on recent performance

### Mobile-First Design
- Large touch targets for easy use while moving
- No-zoom design prevents accidental scaling
- Works offline once loaded
- Responsive layout optimized for smartphones

### Time Management
- **Projected vs Actual**: Compare planned times with actual performance
- **Difficulty-Adjusted Pacing**: Accounts for terrain difficulty in calculations
- **Fuel Station Delays**: Automatically adds 1-minute delays at fuel stations

### Social Sharing
- **One-Tap Updates**: Generate pre-formatted messages for WhatsApp/SMS
- **Smart Status Messages**: Automatically includes pace comparison (ahead/behind/on track)
- **Example**: "🏃‍♀️ Rhona has just passed the 40.5km mark at 09:15:30 and is projected to finish at 14:35. She's running faster than planned! 💪"

### Performance Logging
- **Automatic Time Logging**: Every recorded time is saved with context
- **Performance Delta**: Shows +/- time difference from plan
- **Complete History**: Review all checkpoints after the race
- **Export Ready**: Access full data for post-race analysis

## 📱 How to Use

1. **Set Start Time**: Default is 05:15 AM (adjustable)
2. **Track Progress**: Tap any 500m segment as your runner passes
3. **Record Time**: Enter the actual time or confirm the projected time
4. **Share Updates**: Tap "Share Update" to copy a formatted message
5. **View History**: Access all recorded times via "View Logs" button

## 🛠️ Technical Details

- **Pure HTML/CSS/JavaScript**: No dependencies or build process required
- **LocalStorage**: Persists race logs between sessions
- **Responsive Design**: Adapts to any screen size
- **Offline Capable**: Works without internet once loaded

## 📊 Race Data

The tracker includes the full Comrades Marathon route with:
- 18 tracked sections (5km each)
- Difficulty ratings for each section
- Major landmarks (Big Polly's, Drummond, Fields, Cowies, etc.)
- Fuel station locations

## 🚀 Quick Start

### Option 1: Direct Link
Visit: `https://[your-username].github.io/comrades-race-tracker/`

### Option 2: Download and Run Locally
1. Download `index.html`
2. Open in any modern web browser
3. Bookmark for offline use

### Option 3: Host Your Own
1. Fork this repository
2. Enable GitHub Pages in Settings
3. Share your personalized link

## 📝 Customization

To customize for your runner:
1. Edit line 746: Change "Rhona" to your runner's name
2. Adjust the base pace (currently 6:27/km) if needed
3. Modify difficulty factors based on your runner's strengths

## 🤝 Contributing

Feel free to fork and enhance! Some ideas:
- Add weather conditions tracking
- Include split comparisons with previous years
- Add photo upload capability
- Create runner profiles for multiple athletes

## 📄 License

MIT License - Feel free to use and modify for your own races!

## 🏆 About Comrades

The Comrades Marathon is an iconic 89km ultra-marathon between Durban and Pietermaritzburg in South Africa. This tracker helps support crews provide accurate updates throughout the grueling "Ultimate Human Race."

---

**Built with ❤️ for Comrades runners and their support crews**
