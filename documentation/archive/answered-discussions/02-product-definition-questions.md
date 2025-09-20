# Clarifying Questions for Repaso

## Product Definition Questions

**Core Functionality**
1. Should the AI generate different types of flashcards (multiple choice, fill-in-blank, simple Q&A) or focus on one type initially? multiple

2. What content sources are most important to support first? (Text files, PDFs, web pages, manual input) text files, web pages, manual input

3. How much control should users have over the AI generation process? (Full automation vs user review/editing) it's configutable including on the individual subject level.

**User Experience**
4. What devices/platforms are priority? (Mobile app, web app, desktop app) all

5. Should users organize flashcards into decks/subjects, or keep it simpler? into subjects, which then have modules, which then have sections and lessons. suggest better hierarchy if possisble, if that would make more sense to the majority of people in the world. 

6. How important is offline functionality for studying? not initailly but nice to have. 

**Language School Integration**
7. How do you envision words from language lessons flowing into flashcards? (Manual selection by teacher, automatic processing of lesson materials, student input during class) api, our app just accepts the words.

8. Should the language school integration be built from the start, or added later? later. repaso is not aware of this integration. it just knows it can get sth via api

9. What languages are most important to support initially? does not matter.

## Technical Questions

**AI Integration**
10. Are you comfortable with API costs for AI generation, or should we consider running smaller models locally? i'd consider both, but not sure devops effort for this.

11. Should the AI generation be instant, or is it OK if it takes a few seconds to process content? few seconds to a minute, streaming should update the ui incrementally as cards get generated.

**Data & Privacy**  
12. How important is user data privacy? (Store everything locally vs cloud-based with sync) sync of course.

13. Should users be able to share their flashcard decks with others? yes but it's not important now. 

## Business Questions

**Monetization**
14. Are you thinking freemium (free with limits) or paid from the start? free with severe limits so users try their flashcards. the more resources you use to generate flashcards the mcloser you're to hitting the limit. 

15. What would make this worth paying for versus free alternatives like Anki? API access, AI generation of cards, knowledge maintenance including through AI, nudges from AI about your cards, stimulating learning.

**Competition**
16. What do you dislike most about existing flashcard apps? manual input of decks, lack of hierarchy structure, lack of quick input , coding cards are hard to create.

17. What would make someone switch from their current solution? AI integration, immediate import from their system into ours.

18. our competitiors are also languge learning apps.

---

*Please answer whichever questions feel most important to you. We don't need to tackle everything at once - just enough to define the first steps.*