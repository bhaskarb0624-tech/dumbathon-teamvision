# MADLOG - Fast Prototype Demo Timings

## ⚡ Quick Demo Configuration

Perfect for presentations and demonstrations!

### Stage Progression (Total: ~1 minute)

| Stage | Name | Duration | Total Time | Key Features |
|-------|------|----------|------------|--------------|
| **Stage 1** | Normal | **15 seconds** | 0:00 - 0:15 | Clean interface |
| **Stage 2** | Paranoid | **15 seconds** | 0:15 - 0:30 | Popups + Still Alive |
| **Stage 3** | Sarcastic | **15 seconds** | 0:30 - 0:45 | Shake + Red overlay |
| **Stage 4** | Insanity | **5+ seconds** | 0:45 - 0:50+ | Maximum chaos |

### Still Alive System (Fast)

- **Check Interval**: Every 20 seconds (was 60s)
- **Grace Period**: 5 seconds (was 15s)
- **Total Time**: 25 seconds before deletion
- **Content Deleted**: Last 20 seconds of typing

### Auto-Save

- **Snapshot Interval**: Every 5 seconds (was 10s)
- **Recovery Window**: 20 seconds (was 60s)
- **Max Snapshots**: 10

### Secret Ending

- **Trigger Time**: 50 seconds (was 5 minutes)
- **Activates**: After Stage 4

## 🎯 Demo Timeline

```
0:00 ━━ START - Stage 1 (Normal)
     │  Clean interface, no sounds
     │
0:15 ━━ Stage 2 (Paranoid) + Heartbeat sound
     │  Popups begin spawning
     │  Still Alive system activates
     │  Action-blocking popups (70% chance)
     │
0:20 ━━ First "Still Alive" button appears
     │  User has 5 seconds to click
     │
0:30 ━━ Stage 3 (Sarcastic) + Deep Rumble
     │  Screen shaking starts
     │  Red overlay appears
     │  Metallic screeches, glitches
     │  More aggressive sounds
     │
0:40 ━━ Second "Still Alive" check
     │
0:45 ━━ Stage 4 (Insanity)
     │  Heavy shake
     │  Hacker breach sequence
     │  Demonic voice + Alarm + Scream
     │  Extreme chaos sounds
     │
0:50 ━━ Secret Ending Triggers
     │  All entries corrupted
     │  Memory rewritten
     │
1:00+ ━ Continue in Stage 4 chaos
```

## 📊 Quick Stats

- **Total Demo Time**: ~1 minute
- **Stage Changes**: 3 transitions
- **Still Alive Checks**: 2-3 times
- **Secret Ending**: At 50 seconds
- **Sounds**: 15+ different effects
- **Popups**: Exponentially increasing

## 🎮 Demo Script

### 0:00 - 0:15 (Stage 1)
1. Open app
2. Start typing journal entry
3. Show clean interface
4. Mention "no interruptions yet"

### 0:15 - 0:30 (Stage 2)
5. Stage changes - heartbeat plays
6. Popups start appearing
7. Try to save - action-blocking popup
8. Still Alive button appears at 0:20
9. Click it to demonstrate

### 0:30 - 0:45 (Stage 3)
10. Deep rumble plays
11. Screen starts shaking
12. Red overlay appears
13. Metallic screeches
14. More popups spawn
15. Second Still Alive check

### 0:45+ (Stage 4)
16. Hacker breach sequence
17. Multiple loud sounds
18. Heavy screen shake
19. Maximum chaos
20. Secret ending at 0:50

## 💡 Demo Tips

1. **Have audio ready** - Sounds are LOUD
2. **Type continuously** - Shows Still Alive deletion
3. **Close popups** - Demonstrates virus multiplication
4. **Save entries** - Shows action-blocking
5. **Wait for ending** - Full experience in 50 seconds

## 🔄 Reset Between Demos

```javascript
// In browser console
localStorage.clear();
location.reload();
```

## ⚙️ Revert to Original Timings

To restore original 5-minute experience, change in `MadlogApp.tsx`:

```typescript
// Stage progression
setTimeout(() => setStage(2), 60000),   // 1 min
setTimeout(() => setStage(3), 180000),  // 3 min
setTimeout(() => setStage(4), 300000),  // 5 min

// Still Alive
const remaining = Math.max(0, 60 - Math.floor(elapsed / 1000));
if (elapsed >= 60000 && !showStillAlive) // 60s
if (elapsed >= 75000 && showStillAlive)  // 75s

// Secret ending
if (elapsed > 295000 && !memory.current.endingTriggered)
```
