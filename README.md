# Mobile Ad Fraud Security Research Challenge

## Overview
This repository contains my work for a Mobile App Ad Fraud Investigation assessment, where I analyzed iOS and Android applications to identify botnets, spoofed traffic, and suspicious ad behaviors.

## Assessment Details
- **Role**: Ad Fraud Security Researcher
- **Duration**: 3-5 hours (completed over 7 days)
- **Platforms**: Android & iOS

## iOS Investigation

### Apps Analyzed
- com.peoplefun.wordcross (Wordscapes)
- com.feelthemusi.musi (unavailable for download)
- com.coloring.color.number.ios (Happy Color)
- com.zynga.WordsWithFriends3

### Target Bundle IDs Investigated for Spoofing
- 398436747 (Fooducate: Nutrition Coach)
- 6502331592 (Crazy Screws: Wood Bolts & Nuts)
- 1446328948 (How Much Does My Crush Like Me)
- 548598994 (Spades V+)
- 1602458018 (ThemeKit: Widget & Icon Themes)
- 1638678612 (LockWidget: Lock Screen,Themes)
- 1035199024 (Kika Keyboard)
- 1454398991 (Groovepad)
- 520502858 (myTuner Radio)
- 1196764367 (Words With Friends)

### Tools Used
- Proxyman for iOS traffic interception
- Apple iTunes Lookup API for metadata collection
- JSON formatter for API response analysis

### Key Findings
- No bundle ID spoofing detected
- Discovered ad fraud through request multiplication (19+ billing events per single click)
- Multi-network fraud coordination between Amazon and LiftOff
- Excessive SDK traffic patterns

## Android Investigation

### Apps Analyzed
- io.supercent.downhill
- io.supercent.plinko (unavailable)
- com.appmind.radios.it
- radio.online.romania
- word.find
- com.hwg.idlepainter

### Tools Used
- Android Studio with AVD (API 30/31)
- Charles Proxy for network analysis
- MobSF for static analysis
- APKPure for app downloads

### Key Findings
- **Confirmed botnet operation** with coordinated SDK-level spoofing
- Local network infrastructure sharing (192.168.29.x addresses)
- Cross-category API contamination (word games accessing radio APIs)
- Global infrastructure via performaized.com CDN
- 100% of apps using pangolin16.sgsnssdk.com (Pangle SDK)

## Process Documentation

### iOS Testing Process
1. Configured Proxyman with SSL certificates
2. Installed and monitored target apps
3. Captured network traffic during 10-15 minute sessions
4. Analyzed traffic for spoofing indicators

### Android Testing Process
1. Set up Android emulator with proxy configuration
2. Downloaded APKs from APKPure
3. Performed dynamic network analysis with Charles Proxy
4. Attempted static analysis with MobSF
5. Documented shared infrastructure patterns

## Deliverables
- Android Mobile Ad Fraud Investigation Report
- iOS Assessment Walkthrough with screenshots
- Android Assessment Process Walkthrough
- Network traffic captures and analysis

## Detection Recommendations
- Monitor request velocity to ad endpoints
- Implement transaction ID deduplication
- Track cross-network correlations
- Flag SDK version mismatches
- Detect local network proxy usage patterns

## Confidence Levels
- **Android**: 95%+ certainty of intentional coordinated botnet
- **iOS**: Confirmed ad fraud through request multiplication, no bundle ID spoofing

---
*Assessment completed as part of Ad Fraud Security Researcher evaluation*
