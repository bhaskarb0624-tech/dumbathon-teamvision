# MADLOG - Core Functionality Test Document

## 🎯 Purpose

This document verifies that **all core journal features remain fully functional** despite all "dumb challenges" being implemented.

## ✅ Core Requirements

Users must be able to:
1. ✅ Create journal entries
2. ✅ Edit journal entries
3. ✅ Save journal entries
4. ✅ View journal entries
5. ✅ Delete journal entries

**All features must work through ALL madness stages and challenges.**

---

## 📋 Test Suite

### Test 1: Create Entry (Stage 1 - Normal)

**Objective**: Verify basic entry creation works

**Steps**:
1. Open http://localhost:3000/
2. Type title: "Test Entry 1"
3. Type content: "This is my first test entry"
4. Click "[ SAVE ENTRY ]"

**Expected Results**:
- ✅ Entry saves successfully
- ✅ Status message: "Entry saved. Being analyzed..."
- ✅ Title and content fields clear
- ✅ Entry count increases

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 2: Create Entry with Action-Blocking Popup (Stage 2)

**Objective**: Verify entry creation works through action-blocking popup

**Steps**:
1. Wait 15 seconds for Stage 2
2. Type title: "Test Entry 2"
3. Type content: "Testing with popup interference"
4. Click "[ SAVE ENTRY ]"
5. **Action-blocking popup appears** (70% chance)
6. Click "[ ACKNOWLEDGE & PROCEED ]"

**Expected Results**:
- ✅ Popup appears with apocalypse message
- ✅ Backdrop prevents other interactions
- ✅ After dismissing popup, entry SAVES successfully
- ✅ Entry appears in entries list
- ✅ Content is preserved exactly as typed

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 3: View All Entries

**Objective**: Verify entries list displays correctly

**Steps**:
1. Click "[ VIEW ENTRIES: X ]" tab
2. Observe all saved entries

**Expected Results**:
- ✅ All previously saved entries visible
- ✅ Each entry shows: title, timestamp, content preview
- ✅ EDIT and DEL buttons present on each entry
- ✅ Entries sorted by most recent first

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 4: Edit Entry (Stage 2 - With Popups)

**Objective**: Verify editing works with chaos popups active

**Steps**:
1. In "VIEW ENTRIES" tab, click "EDIT" on first entry
2. **Action-blocking popup may appear**
3. If popup appears, dismiss it
4. Modify title to: "Edited Test Entry"
5. Modify content to: "This content has been edited"
6. Click "[ SAVE CHANGES ]"
7. **Action-blocking popup may appear again**
8. If popup appears, dismiss it

**Expected Results**:
- ✅ Edit view loads after dismissing popup (if any)
- ✅ Title and content fields populated with entry data
- ✅ Changes save successfully after dismissing popup (if any)
- ✅ Returns to entries list
- ✅ Entry shows updated title and content
- ✅ Timestamp remains original

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 5: Create Entry During Still Alive Challenge (Stage 2)

**Objective**: Verify saved entries are NOT affected by Still Alive timeout

**Steps**:
1. Go to "[ WRITE ]" tab
2. Type title: "Test Entry 3"
3. Type content: "Testing Still Alive interaction"
4. Click "[ SAVE ENTRY ]" and dismiss any popup
5. Wait for "Still Alive" button to appear (20 seconds)
6. **DO NOT CLICK** the Still Alive button
7. Wait for timeout (25 seconds total)
8. Go to "[ VIEW ENTRIES ]" tab

**Expected Results**:
- ✅ Entry 3 was saved successfully
- ✅ Entry 3 appears in entries list
- ✅ Entry 3 content is intact and unchanged
- ✅ Still Alive timeout does NOT delete saved entries
- ✅ Only unsaved textarea content is affected

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 6: Delete Entry (Stage 3 - Sarcastic)

**Objective**: Verify deletion works during screen shake and chaos

**Steps**:
1. Wait 30 seconds for Stage 3 (screen shaking, red overlay)
2. Go to "[ VIEW ENTRIES ]" tab
3. Click "DEL" on any entry
4. **Action-blocking popup may appear**
5. If popup appears, dismiss it

**Expected Results**:
- ✅ Popup appears with apocalypse message (70% chance)
- ✅ After dismissing popup, entry DELETES successfully
- ✅ Entry removed from list
- ✅ Entry count decreases
- ✅ Deletion persists after page refresh

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 7: Create Entry During Maximum Chaos (Stage 4)

**Objective**: Verify core functionality during most intense stage

**Steps**:
1. Wait 45 seconds for Stage 4 (heavy shake, extreme sounds)
2. Close any chaos popups using panic button (hidden "·" in nav)
3. Go to "[ WRITE ]" tab
4. Type title: "Stage 4 Test"
5. Type content: "Testing during maximum chaos"
6. Click "[ SAVE ENTRY ]"
7. Dismiss action-blocking popup if it appears

**Expected Results**:
- ✅ Can type despite screen shaking
- ✅ Can click save button
- ✅ Popup dismisses successfully
- ✅ Entry saves successfully
- ✅ Entry appears in list with correct content

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 8: Edit Entry During Hacker Breach

**Objective**: Verify editing works during breach sequence

**Steps**:
1. During Stage 4, wait for hacker breach sequence
2. After breach completes, go to "[ VIEW ENTRIES ]"
3. Click "EDIT" on any entry
4. Dismiss popup if appears
5. Make changes to content
6. Click "[ SAVE CHANGES ]"
7. Dismiss popup if appears

**Expected Results**:
- ✅ Edit functionality works after breach
- ✅ Changes save successfully
- ✅ Entry updates correctly

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 9: Persistence Test

**Objective**: Verify entries persist across page refresh

**Steps**:
1. Note the number of entries in "[ VIEW ENTRIES ]"
2. Note the title of the first entry
3. Refresh the page (F5 or Ctrl+R)
4. Go to "[ VIEW ENTRIES ]" tab

**Expected Results**:
- ✅ Same number of entries present
- ✅ All entry titles and content intact
- ✅ Timestamps unchanged
- ✅ No data loss

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 10: Multiple Rapid Operations

**Objective**: Verify system handles rapid create/edit/delete operations

**Steps**:
1. Create 3 entries rapidly (dismiss popups as needed)
2. Edit 2 of them (dismiss popups as needed)
3. Delete 1 entry (dismiss popups as needed)
4. Verify final state

**Expected Results**:
- ✅ All operations complete successfully
- ✅ Final entry count is correct
- ✅ Edited entries show updated content
- ✅ Deleted entry is gone
- ✅ No errors or data corruption

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 11: Entry Content Integrity

**Objective**: Verify entry content is never corrupted by challenges (except secret ending)

**Steps**:
1. Create entry with special characters: "Test!@#$%^&*()"
2. Create entry with long text (500+ characters)
3. Create entry with keyword "water" (triggers silent corruption)
4. Save all entries
5. View entries and check content

**Expected Results**:
- ✅ Special characters preserved
- ✅ Long text saved completely
- ✅ "water" keyword entry shows: "water... but something is wrong with it."
- ✅ All other content unchanged
- ✅ No unexpected modifications

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 12: Navigation During Chaos

**Objective**: Verify tab navigation works at all times

**Steps**:
1. During any stage with active popups
2. Click between "[ WRITE ]" and "[ VIEW ENTRIES ]" tabs multiple times
3. Close popups as needed

**Expected Results**:
- ✅ Tab switching works immediately
- ✅ View changes correctly
- ✅ No navigation blocked by popups
- ✅ Content preserved when switching tabs

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 13: Empty Entry Validation

**Objective**: Verify system prevents saving empty entries

**Steps**:
1. Go to "[ WRITE ]" tab
2. Leave title and content empty
3. Click "[ SAVE ENTRY ]"

**Expected Results**:
- ✅ Warning message: "Entry cannot be empty. Or can it?"
- ✅ Entry NOT saved
- ✅ No popup appears
- ✅ Entry count unchanged

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 14: Cancel Edit Operation

**Objective**: Verify cancel button works in edit mode

**Steps**:
1. Go to "[ VIEW ENTRIES ]"
2. Click "EDIT" on any entry
3. Dismiss popup if appears
4. Make changes to content
5. Click "[ CANCEL ]" button

**Expected Results**:
- ✅ Returns to entries list
- ✅ Changes NOT saved
- ✅ Original entry unchanged
- ✅ No data loss

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

### Test 15: Secret Ending - Corruption (50 seconds)

**Objective**: Verify entries are corrupted by secret ending, but still viewable

**Steps**:
1. Wait 50 seconds for secret ending to trigger
2. Secret ending sequence plays
3. Go to "[ VIEW ENTRIES ]" tab
4. Observe entries

**Expected Results**:
- ✅ All entries marked as "[CORRUPTED]"
- ✅ Entry content replaced with corruption messages
- ✅ Entries still visible in list
- ✅ Can still view corrupted entries
- ✅ Cannot edit corrupted entries (no EDIT button)
- ✅ Can still delete corrupted entries

**Actual Results**: ________________

**Status**: ☐ PASS ☐ FAIL

---

## 📊 Test Summary

| Test # | Test Name | Status | Notes |
|--------|-----------|--------|-------|
| 1 | Create Entry (Stage 1) | ☐ PASS ☐ FAIL | |
| 2 | Create with Popup (Stage 2) | ☐ PASS ☐ FAIL | |
| 3 | View All Entries | ☐ PASS ☐ FAIL | |
| 4 | Edit Entry (Stage 2) | ☐ PASS ☐ FAIL | |
| 5 | Still Alive Interaction | ☐ PASS ☐ FAIL | |
| 6 | Delete Entry (Stage 3) | ☐ PASS ☐ FAIL | |
| 7 | Create During Chaos (Stage 4) | ☐ PASS ☐ FAIL | |
| 8 | Edit During Breach | ☐ PASS ☐ FAIL | |
| 9 | Persistence Test | ☐ PASS ☐ FAIL | |
| 10 | Multiple Rapid Operations | ☐ PASS ☐ FAIL | |
| 11 | Content Integrity | ☐ PASS ☐ FAIL | |
| 12 | Navigation During Chaos | ☐ PASS ☐ FAIL | |
| 13 | Empty Entry Validation | ☐ PASS ☐ FAIL | |
| 14 | Cancel Edit Operation | ☐ PASS ☐ FAIL | |
| 15 | Secret Ending Corruption | ☐ PASS ☐ FAIL | |

**Total Tests**: 15  
**Passed**: ___  
**Failed**: ___  
**Pass Rate**: ___%

---

## 🎯 Success Criteria

**PASS**: All 15 tests must pass to confirm core functionality is intact.

**Core functionality is considered working if**:
- ✅ Users can create entries at all stages
- ✅ Users can edit entries at all stages
- ✅ Users can save entries at all stages
- ✅ Users can view entries at all stages
- ✅ Users can delete entries at all stages
- ✅ Action-blocking popups delay but don't prevent actions
- ✅ Still Alive system doesn't affect saved entries
- ✅ Entries persist across page refreshes
- ✅ No data corruption (except intentional secret ending)

---

## 🔧 Testing Environment

- **URL**: http://localhost:3000/
- **Browser**: _________________
- **Date**: _________________
- **Tester**: _________________

---

## 📝 Additional Notes

### Known Intentional Behaviors:
1. **Action-blocking popups** (70% chance in Stage 2+) - This is intentional, action completes after dismissal
2. **Still Alive timeout** - Only deletes unsaved textarea content, never saved entries
3. **Water keyword corruption** - Intentionally modifies "water" to "water... but something is wrong with it."
4. **Secret ending corruption** - Intentionally corrupts all entries at 50 seconds
5. **Chaos popups** - Annoying but don't block core functionality

### What Should NEVER Happen:
- ❌ Saved entries deleted by Still Alive system
- ❌ Entries lost on page refresh
- ❌ Unable to save/edit/delete after dismissing popup
- ❌ Core buttons disabled or non-functional
- ❌ Data corruption before secret ending

---

## 🚨 Bug Report Template

If any test fails, use this template:

**Test Number**: ___  
**Test Name**: _______________  
**Stage**: ___  
**Expected**: _______________  
**Actual**: _______________  
**Steps to Reproduce**:
1. 
2. 
3. 

**Screenshots/Console Errors**: _______________

---

## ✅ Certification

I certify that I have completed all 15 tests and confirm that:

☐ All core journal features work correctly  
☐ Action-blocking popups delay but don't prevent actions  
☐ Still Alive system doesn't affect saved entries  
☐ Entries persist across all stages and page refreshes  
☐ The core feature remains usable after implementing all dumb challenges

**Tester Signature**: _________________  
**Date**: _________________

---

## 🎮 Quick Test (5 Minutes)

If you need a quick verification:

1. **Create** an entry → ✅ Works
2. **Edit** the entry → ✅ Works (dismiss popup if needed)
3. **View** entries list → ✅ All entries visible
4. **Delete** an entry → ✅ Works (dismiss popup if needed)
5. **Refresh** page → ✅ Entries persist

**Quick Test Result**: ☐ PASS ☐ FAIL
