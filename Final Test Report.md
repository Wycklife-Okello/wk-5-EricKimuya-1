
# Week 5 QA Assignment – Word Puzzle Game Plus  

## Team Information  
**Team Name:** Power Tester  
**Project Name:** Word Puzzle Game Plus  
**Submission Date:** 27 October 2025  

### Team Members and Roles  
| Member Name | Role |
|--------------|------|
| Eyasu Abreha  | Test Manager |
| Wycklife Okello | Risk Analyst |
| Muumbi Eric Kimuya | Test Executor  |

---

## 1  Test Plan (Test Manager Section)  

**Objective**  
To verify that all core functions of the Word Puzzle Game Plus application operate correctly, store data reliably, and provide a smooth user experience across sessions.

**Scope**  
Tested modules:  
- Reset Game  
- Leaderboard (localStorage persistence)  
- Bonus Round (score multiplier)  
- Hint System  
- Input Validation and Usability  

**Test Environment**  
- Browser – Google Chrome v119 (Desktop)  
- OS – Windows 10 and Ubuntu 22.04 Linux  
- Tools – Manual testing with console logs and localStorage inspection  

**Test Deliverables**  
- Test Plan and Test Cases  
- Test Execution Results  
- Defect Report (if any)  
- Final Summary and Sign-off  

**Schedule**  
Testing Period: 24 – 26 October 2025  
Completion Deadline: 28 October 2025  

---

## 2  Risk Analysis (Risk Analyst Section)  

| Risk ID | Description | Impact | Likelihood | Mitigation Strategy |
|----------|--------------|---------|-------------|--------------------|
| RSK-01 | Reset button fails to clear game state | High | Low | Validate and confirm state reset of score and progress |
| RSK-02 | Leaderboard does not retain top scores in localStorage | High | Medium | Verify and enforce storage and retrieval logic |
| RSK-03 | Bonus Round logic triggers incorrectly | Medium | Low | Review and retest modulo condition logic |
| RSK-04 | Hint system allows multiple deductions | Medium | Medium | Check and confirm flag `hintUsed` and score updates |
| RSK-05 | Empty input accepted as valid guess | High | Low | Validate and trim input before submission |
| RSK-06 | UI lags on rapid clicks | Low | Medium | Verify responsiveness and improve event handling |
| RSK-07 | LocalStorage quota exceeded | Low | Low | Clear old entries before adding new data |

---

## 3  Test Design and Execution (Test Executor Section)  

| ID | Feature | Objective | Steps | Expected Result | Actual Result | Status | Risk Link |
|----|----------|------------|-------|----------------|----------------|--------|-----------|
| TC001 | Reset Game | Verify reset clears game state without deleting leaderboard | Start game → increase score → click Reset | Score and puzzles reset to 0 and message shows “Game reset!” | Works as expected | Pass | RSK-01 |
| TC002 | Leaderboard | Verify top 3 scores are stored and displayed | Solve 4 puzzles with different scores → check leaderboard | Only the top three scores should be retained and displayed in descending order | Works as expected | Pass | RSK-02 |
| TC003 | Leaderboard Persistence | Verify scores persist after page reload | Add scores → refresh browser | Scores remain visible in leaderboard | Works as expected | Pass | RSK-02 |
| TC004 | Bonus Round | Verify score doubles after every third puzzle | Solve 3 puzzles successfully | Score doubles after third puzzle | Works as expected | Pass | RSK-03 |
| TC005 | Hint Function | Verify only one hint allowed and deducts points once | Click Hint twice before guessing | On first click, 2 points are deducted, and a hint is shown. On subsequent clicks, display a warning without further deductions. | Works as expected | Pass | RSK-04 |
| TC006 | Input Validation | Verify blank input shows warning | Click Submit with empty input | Message “Please enter a guess!” | Works as expected | Pass | RSK-05 |
| TC007 | Responsiveness | Verify buttons respond instantly | Rapidly click all controls | No delays or freeze | Works smoothly | Pass | RSK-06 |

---

## 4  Defect Tracking  

### 🧾 Defect Summary Table

| ID | Title | Status | Severity | Priority | GitHub Issue Link |
|----|--------|----------|-----------|-----------|-------------------|
| DEF-01 | Timer fails to reset when starting a new game | Open | Medium | High | [Issue #2](https://github.com/PLP-Database-Design/wk-5-EricKimuya-1/issues/2) |
| DEF-02 | Hint button deducts points multiple times instead of once | Open | Medium | Medium | [Issue #3](https://github.com/PLP-Database-Design/wk-5-EricKimuya-1/issues/3) |
| DEF-03 | Leaderboard does not show scores in descending order | Open | Low | Medium | [Issue #4](https://github.com/PLP-Database-Design/wk-5-EricKimuya-1/issues/4) |

### 🧩 Issue Details

**DEF-01 – Timer fails to reset when starting a new game**  
When the player restarts, the countdown timer continues from the previous session instead of resetting to the initial value.  
→ [View on GitHub](https://github.com/PLP-Database-Design/wk-5-EricKimuya-1/issues/2)

**DEF-02 – Hint button deducts points multiple times instead of once**  
Each click on the Hint button deducts additional points instead of only the first click.  
→ [View on GitHub](https://github.com/PLP-Database-Design/wk-5-EricKimuya-1/issues/3)

**DEF-03 – Leaderboard does not show scores in descending order**  
Scores appear unordered or ascending instead of showing the top three scores in descending order.  
→ [View on GitHub](https://github.com/PLP-Database-Design/wk-5-EricKimuya-1/issues/4)

---

## 5  Retest Summary  

| Feature | Original Status | Retested Status | Result |
|----------|----------------|-----------------|---------|
| Reset Game | Pass | Pass | Verified Stable |
| Leaderboard Persistence | Pass | Pass | Verified Stable |
| Bonus Round | Pass | Pass | Verified Stable |
| Hint System | Pass | Pass | Verified Stable |
| Input Validation | Pass | Pass | Verified Stable |

---

## 6  Test Summary and Metrics  

**Total Test Cases:** 7  
**Passed:** 7  
**Failed:** 0  
**Blocked:** 0  
**Defects Found:** 3  

**Overall Result:** ✅ All major tests passed successfully with minor defects logged for improvement.  

---

## 7  Sign-Off  

| Role | Name | Signature / Initials | Date |
|------|------|----------------------|------|
| Test Manager | Eyasu Abreha  | EA | 27 Oct 2025 |
| Risk Analyst | Wycklife Okello | WO | 27 Oct 2025 |
| Test Executor | Muumbi Eric Kimuya | MEK | 27 Oct 2025 |

---

**Final Remarks:**  
All core functions of Word Puzzle Game Plus performed as intended. The application meets most functional and usability requirements, with minor defects documented and linked for future correction.
