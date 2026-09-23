# The Unofficial Guide

<!-- Replace this line with your name and which corpus you picked. -->

> **This file is your submission.** Fill it in as you go — most sections get
> written during the milestone that produces them, not at the end.
>
> How the starter works, and every command you'll need, is in `RUNNING.md`.
> Leave that file alone.
>
> **Paste everything as text.** No screenshots, no video. A typed table gets
> full credit; a picture of the same table gets none.
>
> Delete these instruction blocks as you replace them. The `<!-- -->` comments
> are notes to you and don't show up when the page renders — you can leave them
> or remove them.

---

# Unit 1

## What This Does

<!-- For this project I picked the corpus called advice_threads. When picking this corpus I asked questions that pertained to information that can be found in this corpus. For example transfering credits, when you can declare a course late, What does students say about Ridgeway Cafe and many more. This system is designed to be able to take a question you may have and provide an answer to your question. If there is a question that doesn't have information provided in the advice_threads, then the system will prompt disclose not having enough information.  -->

## Chunking Strategy

**Chunk size:** 150-250 
**Overlap:** 0 

<!-- The documents in our dataset are short online forum posts and threads. Since these posts are short and have casual sentences, setting a stricter character limit and splitting strictly at sentence boundaries I ensure each chunk comtains a complete thought. This range is large enough to capture a full forum reply but small enough to prevent completely different student topics from getting blended together into the same chunk. -->

## Sample Chunks

**Chunk 1** 
======================================================================
Chunk 1  |  source: thread_bike_commute.txt#0  |  produced by: chunker.py::fallback_split
======================================================================

```THREAD: Is a bike worth it for a 20 minute walk commute?

--- reply 1 (14 votes) ---
Yeah. Cuts an 18 minute walk to about 6. The thing nobody mentions is storage — covered bike parking exists at three buildings and is full by 9am at all three.

--- reply 2 (9 votes) ---
Counterpoint, I sold mine. Between November and March the paths are either icy or salted and salt destroys a drivetrain in one season.

--- reply 3 (22 votes) ---
Both true. I keep a cheap bike for September to November and walk the rest of the year. Total cost was about $120 for the bike and I don't care what happens to it.

--- reply 4 (5 votes) ---
If you do get one, the campus does free registration and it's the only reason I got mine back after it was taken.
```

**Chunk 2** 
======================================================================
Chunk 2  |  source: thread_first_gen.txt#0  |  produced by: chunker.py::fallback_split
======================================================================

```THREAD: Anything specific for first-generation students?

--- reply 1 (33 votes) ---
The advising office has a specific programme and it is genuinely good, but it is opt-in and badly publicised. Ask for it by name.

--- reply 2 (41 votes) ---
The thing I'd say: the unwritten rules are the hard part, not the coursework. Ask about the unwritten rules explicitly. People are happy to explain them and nobody volunteers them.

--- reply 3 (16 votes) ---
Emergency fund for textbooks and travel exists and is not means-tested beyond a short form.
```

**Chunk 3**
======================================================================
Chunk 3  |  source: thread_laptop_specs.txt#0  |  produced by: chunker.py::fallback_split
======================================================================

```THREAD: How much laptop do I actually need for CS courses?

--- reply 1 (31 votes) ---
Less than the recommended spec page says. 16GB of RAM is the one number worth paying for; everything else you'll never notice.

--- reply 2 (18 votes) ---
Adding: the lab machines exist and are better than anything you'll buy. For the heavy assignments people just use those.

--- reply 3 (12 votes) ---
I did two years on an 8GB machine and it was fine until the last project, at which point it very much wasn't. 16 is the answer.
```

**Chunk 4**
======================================================================
Chunk 4  |  source: thread_office_hours_etiquette.txt#0  |  produced by: chunker.py::fallback_split
======================================================================

```THREAD: Is it weird to go to office hours with no specific question?

--- reply 1 (44 votes) ---
No, and this is the single most common thing first years get wrong. 'I'm following the lectures but I don't feel like I understand the shape of it' is a completely normal thing to say.

--- reply 2 (29 votes) ---
They're usually empty. You are doing the instructor a favour by turning up.

--- reply 3 (18 votes) ---
If it helps, treat it as a standing appointment. Go every week for a month and it stops feeling like a thing.
```

**Chunk 5** 
======================================================================
Chunk 5  |  source: thread_roommate_conflict.txt#0  |  produced by: chunker.py::fallback_split
======================================================================

```THREAD: Roommate situation isn't working. What now?

--- reply 1 (28 votes) ---
Talk to your RA early, and frame it as 'we need help sorting this out' rather than 'move me'. Room changes are possible but the process starts with mediation and skipping that step slows it down.

--- reply 2 (14 votes) ---
Room changes happen at the semester boundary almost always, and mid-semester only in fairly serious cases.

--- reply 3 (33 votes) ---
Write down specifics before the meeting. 'It's not working' is hard to act on; 'guests four nights a week past 2am' is not.
```

## Sample Answer
**Question:**
```
Where is the best place to study?

```
**Answer:**

```Based on the provided documents, there is no single "best" place to study, but several spots are recommended depending on your needs:

* **Ridgeway Café** before 10am is noted as empty, quiet, with good coffee (thread_study_spots.txt).
* **Open lounges** on floors 2 through 5 of the science building are unlocked and almost always empty (thread_study_spots.txt).
* **The library third floor** is recommended if you need reliable silence (thread_study_spots.txt).
* **Library group study rooms** can also be booked by one person and used alone (thread_study_spots.txt).
```

**My relevance cutoff:**

<!-- When looking at the best distance, my relevance cutoff would be 0.55. The reason I chose 0.55 is because all five of my valid in-corpus questions had a best distance score of 0.504 or lower. Compared to my out-of-scope trick questions scored 0.617 or higher. Which set the threshold at 0.55, seperating real questions from off-the-scope ones. -->

| Question | In corpus? | Best distance |
|"Up to how many weeks can you take to declare a course late?"|yes|best distance 0.458|
|"Would transfering credits be hard if I only took general requirements?|yes|best distance 0.372|
|What would students say about Ridgeway Cafe for studying?|yes|best distance 0.403|
|How much percentage do some professors take off each day it's late?|yes|best distance 0.395
|Are office hours more effective when wanting to reach out to a proffesor?|yes|best distance 0.504
|Does the app show accurate machine availability?|no|best distance 0.617
|What can I talk to my RA about?|no|best distance 0.729
|What should I do if I need an extension?|no|best distance 0.816
|If I have problems with my group what should I do?|no|best distance 0.643,
|Where is considered the best place to eat?|no|best distance 0.735
## How I Used AI

**1.**
```
I asked Google gemini to explain to me certain terminology about this project. For example, what is corpus, or what was chunks. Even though this may seem simple to some, for me I struggled when it came to understanding what I was doing fundamentally and after asking AI, I was able to get a ground understaning on what to expect in this project. 
```

**2.**
```
I asked Claude to help me to evaluate the code I wrote in chunker.py. I asked Claude to look through my code and make sure it made sense and was doing what I needed the code to do. At first Claude prompted to rewrite my whole code but I didn't want it to rewrite my whole code. I just wanted suggestions how to improve my code. But with being persistant and changing up my wording, I was able to get the advice I needed.  
```

<!-- ── Stretch features ─────────────────────────────────────────────────────
     Doing one? Say so here BEFORE you start. A feature this README never
     claims earns nothing.
     ───────────────────────────────────────────────────────────────────────── -->

---

# Unit 2

<!-- These sections get ADDED to what's already above. Don't delete or rewrite
     unit 1 — the point is that someone can see what you said before you knew
     how it went. -->

## Run Log — Before

<!-- Your five criteria, three runs each. `python run_eval.py --label before`
     runs the questions, puts the OUT_OF_SCOPE ones through the gate, and
     writes it all into results/ for you. Targets come from criteria.md; the
     verdict column is your call.

     Criterion 3 is measured in one deterministic pass rather than three, so
     the same number goes in all three run columns. That's correct, not lazy.

     Milestone 1. -->

| Criterion | Target | Run 1 | Run 2 | Run 3 | Verdict |
|---|---|---|---|---|---|
| 1. Retrieved chunk contains the answer | 4 of 5 |  |  |  |  |
| 2. Every answer names a source | 5 of 5 |  |  |  |  |
| 3. Gate stops out-of-corpus questions | 4 of 5 |  |  |  |  |
| 4. |Average Chunk Size  | | | | |
| 5. |Speed | | | | |

<!-- Underneath, paste the REAL output for each criterion from one of your
     runs — the actual text your system produced, not a description of it.
     Name the file and function that produced it. -->

## Verdicts

<!-- MET or MISSED for each of the five, against the target you wrote last
     unit — not a new one. Plus a sentence on how you decided. That sentence
     matters most where it was close.

     If your target said 4 of 5 and your runs came out 4, 3, 4, that's a MISS.
     The target has to hold, not show up occasionally.

     Milestone 2. -->

| # | Criterion | Verdict | How I decided |
|---|---|---|---|
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |

## Diagnoses

<!-- For each miss: which stage caused it, and how. The stage alone isn't
     enough — you need the mechanism.

     Not a diagnosis: "Question 3 didn't work."
     A diagnosis:     "Question 3 asks about laundry costs. The answer is in
                       one sentence that got split across two chunks, so
                       neither chunk on its own contains it."

     The five stages: loading → chunking → embedding → retrieval → generation.

     Look for a pattern. If three misses all ask about numbers, that's one
     problem, not three.

     Missed nothing? Say so, then say honestly whether your targets were set
     low, and which one you'd tighten and to what.

     Milestone 3. -->

## The Improvement

**What I changed:**

**Why I picked it:**

<!-- Connect it to a specific diagnosis above in one sentence. If you can't,
     you picked a fix because it sounded impressive. -->

### Run Log — After

<!-- Same format, same five criteria, three runs each.
     `python run_eval.py --label after` -->

| Criterion | Target | Run 1 | Run 2 | Run 3 | Verdict |
|---|---|---|---|---|---|
| 1. Retrieved chunk contains the answer | 4 of 5 |  |  |  |  |
| 2. Every answer names a source | 5 of 5 |  |  |  |  |
| 3. Gate stops out-of-corpus questions | 4 of 5 |  |  |  |  |
| 4. |Average Chunk Size | | | | |
| 5. |Speed | | | | |

**Did it help?**

<!-- Say plainly whether it did, and how you know. If it made things worse,
     say that — a change that backfired, honestly reported, earns full credit
     and is more interesting than one that worked. What matters is that you can
     tell.

     Milestone 4. -->

## What's Still Broken

<!-- For each criterion still missed after your fix: what you'd do about it,
     and why you stopped where you did.

     When looking at what I missed, the reason I stopped where I did is because I am still confused on what I am trying to do. I also did ran out of time but more so that I needed more explanation on what was expected from me in this project.  -->

## What I'd Do Differently

<!-- After looking at my criteria I would change the first one: "For at least 4 of my 5 test questions, the retrieved chunks include one that contains the answer". The reason I would chnage this criteria in specific is because I believe that the system should only answer if they have the answer. Since 4 out 5 out of the retrieved chunks can have one of the answers, it leaves the user confused and have more questions then answers. 

-->
