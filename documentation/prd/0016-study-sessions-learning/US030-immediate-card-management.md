# US030 - Immediate Card Management During Learning

As a user studying flashcards, I want to quickly manage cards during my learning session so I can handle confusing or problematic cards without interrupting my study flow.

## User Story

I want to be able to mark cards for later review, suspend them entirely, or add quick notes during my study session. This should be fast and intuitive so I can make decisions about cards without breaking my learning rhythm or having to remember to come back to them later.

## Acceptance Criteria

- [ ] Users can mark cards as "to be reviewed" with a single action during study
- [ ] Users can suspend cards entirely to remove them from current session
- [ ] Users can add quick notes to cards without leaving the study interface
- [ ] All actions are available via keyboard shortcuts for speed
- [ ] Marked cards are clearly indicated in the study interface
- [ ] Suspended cards are removed from current session but preserved for later
- [ ] Notes are immediately saved and visible on card review
- [ ] Users can undo recent actions if they change their mind
- [ ] Actions don't interrupt the study session flow

## Business Value

Enables users to maintain focus during study sessions while handling problematic cards efficiently, reducing cognitive load and improving the overall learning experience.

## Technical Requirements

- Quick action buttons/keyboard shortcuts during study
- Immediate state updates without page refresh
- Card state management (marked, suspended, noted)
- Undo functionality for recent actions
- Integration with existing study session flow

## Success Metrics

- Card management action completion rate
- User satisfaction with study session flow
- Time spent on card management vs. actual studying
- Frequency of undo actions (indicates UI clarity)
- User engagement with marked/suspended cards later

## User Stories

1. As a user, I want to mark confusing cards for later review so I can focus on what I know
2. As a user, I want to suspend cards that are too difficult so I can study them when I'm ready
3. As a user, I want to add quick notes to cards so I can remember my thoughts without stopping
4. As a user, I want to undo my actions so I can correct mistakes quickly
5. As a user, I want all actions to be fast so my study rhythm isn't interrupted
