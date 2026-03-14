# MADLOG Testing Guide

## Quick Test Scenarios

### Test 1: Still Alive Button (2 minutes)
1. Open http://localhost:3000
2. Start typing in the journal entry field
3. Watch the status bar - countdown should show "NEXT CHECK: 60s"
4. Wait for countdown to reach 0
5. **Expected**: "Still Alive" button appears at random position
6. **Expected**: Status bar shows "⚠ CONFIRM PRESENCE"
7. Click the "Still Alive" button
8. **Expected**: Button disappears, timer resets to 60s
9. **Expected**: Status message shows "PRESENCE CONFIRMED"

### Test 2: Auto-Deletion (2 minutes)
1. Start typing content in the journal
2. Type continuously for 30 seconds
3. Wait for "Still Alive" button to appear (at 60s mark)
4. **DO NOT CLICK** the button
5. Wait 15 more seconds (total 75s)
6. **Expected**: Content typed in last 60 seconds is deleted
7. **Expected**: Recovery notice appears in top-right corner
8. Click "RECOVER DATA" button
9. **Expected**: Content is restored

### Test 3: Action-Blocking Popups (1 minute)
1. Type some content in the journal
2. Click "SAVE ENTRY" button
3. **Expected**: Apocalypse-themed popup appears with backdrop
4. **Expected**: Popup shows random message (e.g., "RADIATION SPIKE")
5. **Expected**: Entry is NOT saved yet
6. Click "ACKNOWLEDGE & PROCEED" button
7. **Expected**: Popup closes and entry is saved
8. Try editing or deleting an entry
9. **Expected**: Similar blocking popup appears

### Test 4: Auto-Save Recovery (3 minutes)
1. Start typing a long journal entry
2. Type for 20 seconds, then pause
3. Continue typing for another 20 seconds
4. Wait for "Still Alive" button
5. Ignore the button and let timeout occur
6. **Expected**: Content from 60+ seconds ago is preserved
7. **Expected**: Recent content (last 60s) is deleted
8. Click "RECOVER DATA"
9. **Expected**: Full content restored from backup

### Test 5: Madness Stage Progression (6 minutes)
1. Write and save 3 entries quickly
2. **Expected**: Stage advances to 2 (Paranoid)
3. **Expected**: "Still Alive" system activates
4. **Expected**: Action-blocking popups start appearing
5. Write 2 more entries (total 5)
6. **Expected**: Stage advances to 3 (Sarcastic)
7. **Expected**: Screen shaking begins
8. **Expected**: Red overlay appears
9. Wait until 5 minutes total session time
10. **Expected**: Stage 4 (Insanity) activates
11. **Expected**: Heavy shake, rapid popups

### Test 6: Popup Randomization (2 minutes)
1. Save multiple entries in quick succession
2. Note the popup message each time
3. **Expected**: Different apocalypse message each time
4. Messages should include:
   - System warnings
   - Faction alerts
   - Supply shortages
   - Cryptic messages
   - Radiation/biohazard alerts

### Test 7: Timer Visual Indicators (2 minutes)
1. Watch the countdown timer in status bar
2. At 60-30s: **Expected** Green/normal color
3. At 30-15s: **Expected** Orange/warning color
4. At <15s: **Expected** Red color with blinking
5. When button appears: **Expected** "⚠ CONFIRM PRESENCE" text
6. Button should show countdown: "15s", "14s", etc.

### Test 8: Multiple Snapshots (3 minutes)
1. Type content for 10 seconds
2. Pause for 5 seconds (triggers snapshot)
3. Type more content for 10 seconds
4. Pause again
5. Type more content
6. Let "Still Alive" timeout occur
7. **Expected**: Content from oldest snapshot is preserved
8. **Expected**: Recovery available

### Test 9: Core Functionality Persistence (5 minutes)
1. Go through all madness stages
2. At each stage, verify:
   - Can create new entries ✓
   - Can edit existing entries ✓
   - Can delete entries ✓
   - Can view all entries ✓
   - Entries persist after refresh ✓
3. **Expected**: All core features work despite chaos

### Test 10: Edge Cases (3 minutes)
1. **Empty Content**: Try saving empty entry
   - **Expected**: Warning message appears
2. **Rapid Saves**: Save multiple entries quickly
   - **Expected**: Each triggers popup (70% chance)
3. **Button Spam**: Click "Still Alive" multiple times
   - **Expected**: Timer resets, no errors
4. **Recovery Without Backup**: Timeout with no auto-save
   - **Expected**: Content cleared, no recovery notice

## Performance Checks

### Memory Usage
- Open DevTools → Performance
- Monitor for memory leaks during long sessions
- Check localStorage size doesn't grow unbounded

### Timer Accuracy
- Use stopwatch to verify 60-second intervals
- Confirm 15-second grace period is accurate
- Check countdown display updates every second

### Audio Feedback
- Verify sounds play on:
  - Button spawn (static noise)
  - Confirmation (distorted beep)
  - Timeout (static noise)
  - Keyword detection (whisper)

## Browser Compatibility

Test in:
- [ ] Chrome/Edge
- [ ] Firefox
- [ ] Safari
- [ ] Mobile browsers

## Known Behaviors

1. **Auto-save runs every 10 seconds** - This is intentional
2. **Popup chance is 70%** - Some actions may not trigger popup
3. **Recovery only works if snapshots exist** - First 60s has no backup
4. **Timer continues in background** - Even when not on write view
5. **Snapshots limited to 10** - Older snapshots are removed

## Debug Tips

### Check Auto-Save Data
```javascript
// In browser console
JSON.parse(localStorage.getItem('madlog_autosave'))
```

### Check System Memory
```javascript
JSON.parse(localStorage.getItem('madlog_memory'))
```

### Check Entries
```javascript
JSON.parse(localStorage.getItem('madlog_entries'))
```

### Reset Everything
```javascript
localStorage.clear()
location.reload()
```

## Success Criteria

✅ All tests pass without errors
✅ No console errors during normal operation
✅ Timers are accurate within 1 second
✅ Recovery works reliably
✅ Popups block actions correctly
✅ Core journal features always work
✅ Audio feedback plays appropriately
✅ Visual indicators display correctly
✅ No memory leaks during extended use

## Reporting Issues

When reporting bugs, include:
1. Test scenario number
2. Expected behavior
3. Actual behavior
4. Browser and version
5. Console errors (if any)
6. Steps to reproduce
