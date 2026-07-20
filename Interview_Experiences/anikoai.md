# Aniko AI SAT Mentor — Feature Interpretation and Product Analysis

## 1. Core Purpose of Aniko

Aniko appears to be more than a normal SAT chatbot. It is trying to act as a combination of:

**SAT tutor + adaptive practice engine + study planner + progress tracker + light accountability coach.**

Its main goal is to help a student move from their current SAT level to a target score before a chosen examination date.

Its general workflow is:

**Set goal → diagnose current level → identify weak skills → create study plan → assign practice → review mistakes → update mastery → recommend next task**

For a user profile, it may use:

- Target SAT score
- Test date
- Math and Reading/Writing diagnostics
- Daily study workload
- Practice history
- Mistake history
- Timing and difficulty information

---

## 2. Personalized Onboarding

Aniko welcomes the user with personalized information such as:

- User name
- Target SAT score
- Exam date
- Recommended starting actions
- Current setup status

It immediately gives the user several entry points:

- Math diagnostic
- Reading and Writing diagnostic
- Practice test
- Topic-specific practice
- Student profiles
- Leaderboard

### Interpretation

The product does not force every user into one fixed path. It supports different user intentions:

- “I am a beginner.”
- “I already know my weak area.”
- “I want a score estimate.”
- “I just want to practice.”
- “I want to see community activity.”

---

## 3. Goal-Setting System

Aniko stores or uses:

- Target SAT score
- Test date
- Available study time
- Preferred workload
- Math versus Reading/Writing balance

These values form the foundation of the study plan.

For example, a student with:

- 45 days remaining
- Two hours per day
- A target of 1220

should receive a different plan from someone with:

- Six months remaining
- Thirty minutes per day
- A target of 1500

### Important Observation

When the test date was changed to August 22, 2027, Aniko accepted the new date and treated it as the new planning deadline.

This suggests a profile-level settings system, although it must still be verified whether the date is actually saved in the application database or only remembered in the chat.

---

## 4. Diagnostics and Baseline Assessment

Aniko provides two short initial diagnostics:

- Math: 12 questions
- Reading and Writing: 12 questions

The purpose is to create an initial learner profile.

It claims to analyze:

- Correct and incorrect answers
- Question domain
- Specific skill
- Difficulty
- Time taken
- Repeated mistakes
- Consistency across similar questions

### Example

Suppose a student:

- Misses three easy linear-equation questions
- Solves two hard geometry questions
- Takes too long on word problems

Aniko may infer:

- Linear-equation fundamentals are weak
- Geometry is relatively strong
- Mathematical translation or pacing is a concern

### Limitation Found

After the user said that both diagnostics were completed, Aniko asked the user to manually provide the scores.

This could mean:

1. The chat mentor cannot directly access diagnostic results.
2. The diagnostics were not actually completed in the system.
3. The AI lacks reliable integration with the application database.

This should be tested carefully because it determines whether Aniko is a genuinely integrated mentor or mainly a conversational layer.

---

## 5. Personalized Study Plan

Aniko claims to create a day-by-day study plan using:

- Test date
- Target score
- Current estimated score
- Diagnostic performance
- Weak skills
- Available study time
- Preferred subject balance
- Practice-test schedule
- Review requirements

The plan may include:

- Math drills
- Reading and Writing drills
- Vocabulary sessions
- Review Labs
- Short tests
- Full practice tests
- Error review
- Rest or lighter days

### Expected Planning Logic

A probable planning formula is:

**Priority = weakness × SAT importance × urgency × expected score impact**

For example:

- Weak transitions skill
- Frequently tested topic
- Exam is near
- Easy points are available

This should receive higher priority than a rare advanced topic with limited score impact.

### Interpretation

The plan is not merely a calendar. It appears to be a dynamic task-selection system that updates future work according to performance.

---

## 6. Adaptive Learning Engine

This is one of Aniko’s main claimed features.

It says that skill mastery is updated after every question.

### When the User Gets a Question Wrong

Aniko may:

- Assign more questions from the same skill
- Reduce difficulty temporarily
- Test prerequisite concepts
- Add the question to the Error Log
- Schedule it for a Review Lab
- Increase the skill’s priority in the study plan

### When the User Gets Several Questions Right

Aniko may:

- Reduce repetition of that skill
- Increase difficulty
- Move toward advanced applications
- Shift practice toward weaker topics

### Example

If a student repeatedly misses quadratic-equation questions:

1. Aniko detects weak performance in quadratics.
2. It checks factoring and algebra prerequisites.
3. It generates easier quadratic questions.
4. It gradually increases difficulty.
5. It tests the skill later in a mixed session.
6. It updates mastery if performance remains consistent.

### What Must Still Be Verified

The AI described this behaviour, but product testing is needed to confirm whether question selection genuinely changes after correct and incorrect answers.

---

## 7. Skill-Level Practice

The user can practice through a hierarchy:

**Section → Domain → Skill**

Examples:

- Math → Algebra → Linear equations
- Math → Advanced Math → Quadratics
- Reading and Writing → Expression of Ideas → Transitions
- Reading and Writing → Information and Ideas → Inference

Aniko supports:

- User-selected practice
- System-recommended practice
- Difficulty adaptation
- Immediate study sessions
- Weak-skill drills
- Mixed-topic practice

### Product Value

This gives users two modes:

**Manual mode:**  
“I know I am weak in geometry. Let me practice geometry.”

**Adaptive mode:**  
“I do not know what to study. Tell me what will improve my score.”

---

## 8. Practice-Test System

Aniko claims to provide:

- Short practice tests
- Half-length tests
- Full-length tests
- Timed testing
- Section-level scoring
- Timing analysis
- Score estimation
- Post-test review

The practice test serves several purposes:

- More reliable score baseline
- Pacing analysis
- Endurance testing
- Discovery of hidden weaknesses
- Validation of skill mastery
- Progress measurement

### Intended Flow

**Take test → receive score → inspect section breakdown → identify mistakes → open Review Lab → update study plan**

### Potential Issue

The following must be verified:

- Whether tests match the Digital SAT structure
- Whether timing rules are realistic
- Whether score estimates are calibrated
- Whether post-test recommendations actually use test performance

---

## 9. Weakness Detection

Aniko says it identifies weak areas using several signals.

### 9.1 Accuracy

How often the user answers questions from a skill correctly.

### 9.2 Difficulty Weighting

Missing an easy question is treated as more concerning than missing a very hard question.

Getting difficult questions correct gives stronger evidence of mastery.

### 9.3 Repetition

A single error may be noise.

Repeated errors suggest a genuine knowledge gap.

### 9.4 Timing

Possible classifications include:

- Correct but very slow
- Fast but inaccurate
- Slow and inaccurate
- Fast and accurate

Each case should lead to a different recommendation.

### 9.5 Skill Importance

Weaknesses in frequently tested SAT areas should receive higher priority.

### 9.6 Prerequisite Relationships

If a user struggles with quadratics, the true issue may be:

- Factoring
- Algebraic manipulation
- Sign errors
- Function interpretation

A strong adaptive system should distinguish the visible topic from the underlying cause.

---

## 10. Mastery System

Aniko claims to maintain mastery at both domain and skill levels.

A mastery profile may look like:

| Skill | Mastery | Status |
|---|---:|---|
| Linear equations | 82% | Strong |
| Quadratics | 47% | Weak |
| Transitions | 61% | Developing |
| Inference | 38% | Priority weakness |

The mastery score may be affected by:

- Recent answers
- Correctness
- Difficulty
- Time
- Repeated performance
- Review performance
- Practice-test performance

### Important Product Principle

Mastery should not permanently increase after one correct answer.

It should require repeated evidence across:

- Different question styles
- Different difficulty levels
- Different sessions
- Delayed reviews
- Mixed-topic tests

---

## 11. Recommendation Engine

Aniko’s recommendation section appears to update automatically inside the application.

It can recommend:

- Today’s study session
- Weak-skill drill
- Review Lab
- Practice test
- Vocabulary practice
- Bookmarked-question review
- Missed tasks
- Next milestone

### Recommendations Are Reactive, Not Proactive Messages

Aniko stated that it does not proactively send daily recommendation messages.

Instead:

- Recommendations appear on Home or Study Plan.
- The user must open the application.
- The user can message “check-in.”
- Aniko then tells the user what to do next.

### Interpretation

This is an **in-app recommendation system**, not a proactive notification system.

---

## 12. Review System

The review system contains three related features.

### 12.1 Error Log

Stores questions the student answered incorrectly.

It can track:

- Topic
- Skill
- Selected answer
- Correct answer
- Mistake frequency
- Time spent
- Possible error type

### 12.2 Bookmarks

Stores questions manually saved by the user.

This is useful when:

- The user found a question difficult
- The user guessed correctly
- The question contains an important pattern
- The user wants to revisit it

### 12.3 Review Lab

Creates focused review sessions from:

- Wrong answers
- Repeated mistakes
- Weak skills
- Bookmarked questions

### Stronger Version

The user should classify mistakes into:

- Concept gap
- Misread question
- Calculation error
- Time pressure
- Careless mistake
- Guess
- Strategy error

This would allow Aniko to recommend the correct intervention.

For example:

- Concept gap → lesson and foundational drill
- Careless error → checking routine
- Time problem → timed mini-set
- Misreading → question-parsing training

More questions are not always the solution.

---

## 13. Progress Tracking and Analytics

Aniko claims to show:

- Estimated SAT score
- Math score trend
- Reading and Writing score trend
- Mastery by domain
- Mastery by skill
- Accuracy
- Timing
- Study activity
- Activity heatmap
- Streak
- Completed sessions

### What “How Am I Improving?” Should Answer

A useful progress system should explain:

- What improved
- How much it improved
- Why it improved
- What remains weak
- What the user should do next
- Whether the target is still realistic

### Example

> Your transitions accuracy improved from 48% to 71% over the last two weeks. However, inference remains at 43%, and you are taking 22 seconds longer than your target time. Complete two inference drills and one timed mixed set next.

This is more useful than simply showing a graph.

---

## 14. Score Estimation

Aniko claims to maintain a running estimated SAT score.

This estimate may use:

- Practice-test performance
- Skill-level accuracy
- Question difficulty
- Coverage across domains
- Timing
- Recent consistency

### Important Edge Case

A score estimate based on 20 questions should not appear equally reliable as one based on 500 questions.

The system should show:

- Estimated score
- Confidence range
- Evidence volume
- Skill coverage

### Example

> Estimated score: 1210  
> Likely range: 1170–1250  
> Confidence: Medium  
> Reason: Strong Math evidence, limited Reading data

---

## 15. Chat-Based Tutoring

Aniko can act as a concept tutor.

It demonstrated this by teaching quadratic equations through:

- Definition
- Factoring
- Quadratic formula
- Discriminant
- Completing the square
- Worked examples

It can also provide:

- Step-by-step solutions
- Faster SAT methods
- Strategy guidance
- Concept explanations
- High-yield rules
- Follow-up questions
- Easy, medium, or hard practice

### Tutor Roles Visible in the Interaction

Aniko can behave as:

- Explainer
- Problem solver
- Strategy coach
- Study planner
- Recommendation assistant
- Motivation coach

---

## 16. SAT Strategy Feature

Aniko offers strategy-level guidance beyond academic concepts.

Examples include:

- Two-pass solving strategy
- Skip and return
- Question triage
- Guessing strategy
- Avoiding trap answers
- Time benchmarks
- Preventing one difficult question from consuming too much time

### Timing Guidance Provided

It suggested approximately:

- Reading and Writing: 1–1.25 minutes per question
- Math: approximately 1.5 minutes per question
- Skip questions that are taking too long
- Return in the second pass

### Better Personalization

Instead of generic timing advice, it should use the student’s actual history.

Example:

> You average 53 seconds on grammar questions but 104 seconds on inference questions. Save time in grammar and spend more on inference.

---

## 17. Math Preparation Support

Aniko covers:

- Algebra
- Advanced Math
- Data Analysis
- Geometry
- Trigonometry
- Quadratic equations
- Functions
- Linear models
- Unit conversions
- High-yield patterns
- Shortcuts
- Calculator or Desmos strategy

### Potential Advanced Feature

It could recommend the fastest method for each question:

- Mental math
- Algebra
- Plugging in values
- Backsolving
- Desmos
- Graph interpretation

---

## 18. Reading and Writing Support

Aniko supports:

- Main idea
- Inference
- Command of evidence
- Words in context
- Text structure
- Cross-text connections
- Rhetorical synthesis
- Transitions
- Sentence boundaries
- Grammar
- Form, structure, and sense

It can combine:

- Content teaching
- Timed practice
- Error analysis
- Vocabulary
- Reading strategy

---

## 19. Vocabulary Practice

Aniko has a separate Vocab Practice feature.

Its purpose is especially connected to Words-in-Context questions.

A strong implementation should include:

- Spaced repetition
- Example sentences
- Meaning in context
- Similar-word comparison
- Review intervals
- Vocabulary taken from mistakes
- Confidence ratings

---

## 20. Memory Feature

Aniko claims to remember the student through structured learning history rather than only conversational memory.

Its memory appears to include:

- Wrong answers
- Skill mastery
- Practice history
- Timing history
- Bookmarks
- Test scores
- Study-plan settings
- Target score
- Test date

### Two Types of Memory

#### Product Memory

Stored in the application database:

- Scores
- Questions
- Sessions
- Mastery
- Bookmarks
- Error logs

#### Chat Memory

Information remembered during conversation:

- User’s stated intention
- Current concern
- Preferred coaching style
- Temporary discussion context

### Major Concern

Because Aniko asked the user to manually provide diagnostic scores after the user said “done,” the connection between product memory and chat memory may be incomplete.

---

## 21. Scheduling Feature

Aniko claims to schedule:

- Study sessions
- Practice tests
- Review sessions
- Daily workloads
- Specific tasks on specific dates

It can supposedly adjust:

- Workload
- Focus areas
- Subject balance
- Pacing
- Test date
- Target score

### Likely Scheduling Inputs

- Remaining days
- Available hours
- Weakness priorities
- Practice-test frequency
- Review intervals
- User availability

### Important Questions to Test

- Does it understand weekends?
- Can the user block unavailable days?
- Does it reschedule automatically?
- Does it reduce workload after burnout?
- Does it maintain the plan after the test date changes?
- Are calendar dates actually updated in the interface?

---

## 22. Failure Recovery

Aniko says missed days do not reset the plan.

When a user skips a day:

- Progress remains saved.
- Current mastery does not disappear.
- Recommendations continue from the previous state.
- The user can keep the original plan.
- Missed tasks may be moved.
- The user may complete a slightly longer session.

For three missed days, it suggests:

- Avoid recovering the entire backlog at once.
- Complete one useful session.
- Resume normal pacing afterward.

### Interpretation

This is a lightweight failure-recovery model.

### Better Version

A mature recovery system should offer:

- Catch-up mode
- Automatic reprioritization
- Backlog compression
- Revised daily load
- New target feasibility calculation
- Temporary minimum plan
- Recovery reason selection

### Example

> You missed three days because of exams. I removed two low-priority drills, moved your practice test to Sunday, and kept one 20-minute review for today.

---

## 23. Accountability Feature

Aniko provides limited accountability.

It can:

- Ask for a daily commitment
- Set a question target
- Offer strict or supportive coaching
- Run check-ins when the user messages
- Track streaks
- Display statistics
- Show recommended tasks
- Help recover after missed days

It cannot reliably:

- Send proactive daily chat messages
- Send SMS reminders
- Send push reminders through the chat
- Automatically ask why the user missed a session
- Chase the user until a task is completed

### Final Interpretation

Aniko is not currently a complete accountability coach.

It is a **reactive accountability assistant**.

The user must initiate most interactions.

---

## 24. Motivation Features

Built-in motivation appears to include:

- Streaks
- Badges or achievements
- Daily statistics
- Recommended tasks
- Leaderboards
- Student activity
- Challenges
- Chat-based encouragement

Aniko mentioned a previous SAT Lock-In Challenge, which appears to have been a structured accountability campaign.

### Motivation Styles

The chat can adapt to:

- Strict accountability
- Supportive coaching
- Small-win encouragement
- Reset planning after failure

However, it does not appear to have a dedicated proactive motivational-coach module.

---

## 25. Community Features

Aniko includes:

- Student profiles
- Today’s leaderboard
- Activity feed
- Challenge results
- Peer progress visibility

### Possible Benefits

- Social motivation
- Competition
- Proof that others are studying
- Increased engagement
- Community accountability

### Possible Risks

- Anxiety
- Unhealthy comparison
- Privacy concerns
- Cheating or inflated activity
- Demotivation for weaker students

### Better Implementation

A good implementation should support:

- Private mode
- Friends-only leaderboard
- Similar-level peer groups
- Weekly improvement ranking
- Opt-out controls

---

## 26. Product Navigation Knowledge

The mentor knows the names and purposes of internal product features.

It directs users to:

- New Study Session
- New Practice Test
- Review Lab
- Vocab Practice
- Analytics
- Error Log
- Bookmarks
- Study Plan Settings
- Leaderboard
- Students
- Home
- Challenge page

This means Aniko also functions as an **in-product assistant**.

It does not only teach SAT content. It helps the user navigate the application.

---

## 27. Contradictions and Weaknesses Found

### 27.1 “Done” Was Accepted Without Verification

The user told Aniko that both diagnostics were completed.

It accepted the claim and then asked for scores.

This shows weak task verification.

A deeply integrated mentor should be able to respond:

> I can see that you completed Math, but Reading and Writing is still pending.

### 27.2 Possible Confusion Between Profile Data and Chat Statements

Aniko initially had one test date while the user gave another timeline.

It correctly noticed the conflict, which is positive.

However, it still needs to be verified whether the corrected date updated the actual profile.

### 27.3 Repeatedly Pushes Diagnostics

Even when the user’s intention was product research, Aniko repeatedly redirected the conversation toward completing diagnostics.

This may indicate:

- An aggressive onboarding prompt
- Limited intent recognition
- A system instruction prioritizing conversion
- Weak distinction between “use the product” and “explain the product”

### 27.4 Claimed Features May Not Be Implemented

The AI may know feature descriptions from product documentation, but that does not prove every feature works exactly as described.

### 27.5 Accountability Is Weak

There are no reliable proactive reminders.

### 27.6 Memory Integration May Be Incomplete

The chat may not have direct access to all application events and results.

### 27.7 Generic Advice Is Mixed With Personalization

Some strategy advice is generic SAT advice rather than being derived from the user’s actual data.

---

## 28. Confirmed Versus Claimed Features

### Clearly Visible or Strongly Supported

- Goal and test-date awareness
- Diagnostics
- Topic practice
- Practice tests
- Product navigation
- Chat tutoring
- Strategy explanations
- Study-plan discussion
- Leaderboard
- Student profiles
- Recommendations page
- Streaks and statistics
- Error Log
- Bookmarks
- Analytics
- Review Lab
- Vocabulary practice

### Claimed but Requiring Verification

- True adaptive question difficulty
- Automatic mastery updates
- Exact time-based weakness analysis
- Automatic missed-task rescheduling
- Accurate running score estimate
- Direct access to diagnostic results
- Dynamic day-by-day plan regeneration
- External Bluebook score integration
- Automatic prerequisite detection
- Review Labs genuinely generated from personal error data

---

## 29. Overall Product Model

Aniko can be represented through six connected systems:

### 1. Learner Profile

Stores goals, dates, preferences, and history.

### 2. Assessment Engine

Uses diagnostics and practice tests to estimate current level.

### 3. Mastery Engine

Tracks knowledge by domain and skill.

### 4. Recommendation Engine

Selects the next best study task.

### 5. Learning Interface

Provides questions, explanations, tutoring, and review.

### 6. Engagement Layer

Uses scheduling, streaks, leaderboards, motivation, and accountability.

---

## 30. Final Feature Inventory

From the conversation, Aniko contains or claims the following functionalities:

1. Personalized onboarding
2. Target-score setting
3. Test-date setting
4. Daily workload settings
5. Personalized study planning
6. Math diagnostic
7. Reading and Writing diagnostic
8. Short practice tests
9. Half-length practice tests
10. Full practice tests
11. Score estimation
12. Domain-level mastery
13. Skill-level mastery
14. Adaptive question selection
15. Adaptive difficulty
16. Prerequisite remediation
17. Weak-area detection
18. Timing analysis
19. Targeted skill practice
20. Mixed practice
21. Error Log
22. Bookmarks
23. Review Labs
24. Repeated-error detection
25. Analytics dashboard
26. Score trends
27. Accuracy trends
28. Timing trends
29. Activity heatmap
30. Study streak
31. Daily statistics
32. Study scheduling
33. Missed-session recovery
34. Recommended daily tasks
35. SAT strategy guidance
36. Pacing guidance
37. Question-triage guidance
38. Guessing strategy
39. Trap-answer guidance
40. Step-by-step tutoring
41. Math concept teaching
42. Reading and Writing teaching
43. Vocabulary practice
44. High-yield shortcuts
45. Product navigation assistant
46. Check-in support
47. Daily commitment setting
48. Supportive coaching
49. Strict accountability coaching
50. Motivation through gamification
51. Student profiles
52. Leaderboards
53. Activity feed
54. Challenges
55. Study Plan Settings
56. Target and schedule adjustment
57. Optional external score logging
58. Post-test review workflow
59. Personalized next-step recommendations
60. Chat-based mentor support

---

## 31. Final Conclusion

Aniko’s strongest concept is the connection between:

**Assessment → mastery → recommendations → review**

Its weakest area appears to be:

**Proactive accountability and deep integration between mentor chat and actual product activity**

The biggest opportunity for a competing mentor would be:

> Build a mentor that not only knows what the user should do, but also sees whether they did it, proactively follows up, understands why they failed, automatically repairs the plan, and explains every recommendation using real user evidence.
