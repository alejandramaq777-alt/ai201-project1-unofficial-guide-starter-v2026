# Acceptance criteria — The Unofficial Guide

Five criteria that say what "working" means for this system, written in unit 1
**before** any results existed.

An acceptance criterion names a target: a number, a count, a rate, or something
a person could plainly observe. *"Retrieval works"* is an opinion. *"For at
least 4 of my 5 test questions, the top results include a chunk containing the
answer"* is a criterion.

Under each one, write a sentence or two on **why that target** and not a
stricter or looser one. A reason that says something about your corpus or your
pipeline earns credit; *"80% seemed reasonable"* does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## 1. Retrieved chunks contain the answer

For at least 4 of my 5 test questions, the retrieved chunks include one that
contains the answer.

**Why this target:**
<!-- The reason this criteria is important is because it doesn't give a user a half answer or having to do a follow up question to the question they asked. Making it quick for the user to be able to get the answers they are looking for. -->

---

## 2. Every answer names a source

Every answer the system produces names at least one source document.

**Why this target:**
<!-- The reason why the system names where the answer comes from one source document because it allows for the questionnaire to have access to where the answer is coming from. -->

---

## 3. The relevance gate stops out-of-corpus questions

When I ask a question my documents clearly don't cover, the relevance gate
stops it and the system returns "I don't have enough information about that" —
in at least 4 of 5 tries.

<!-- The five questions are the ones in `OUT_OF_SCOPE` at the bottom of
     `questions.py`, and `run_eval.py` puts them through the gate and writes
     what happened into your run log. Swap them for your own if you'd rather —
     just keep five of them, or the "4 of 5" above has nothing to be 4 of. -->

**Why this target:**
<!-- The reason this criteria is important because if there is a question that a user asks that we don't have enough information on, the system should state so. It allows for the user to see what their next question can be or see what we need to add to the system to be able to answer the users questions next time. -->

---

## 4. Something about your chunks

<!-- Average chunk size should stay between 150-250 words to allow meaningful context but also short enough to not overload the user with information. 
 -->



**Why this target:**
<!-- The reason I chose a chunk size of 150-250 because it allows for a meaningful context to be displayed. Giving the user the necessary information that answers their question in a complex matter -->


---

## 5. Your choice

<!-- For at least 4 out of 5 test quieres, the system must generate its complete response in under 3.0 seconds from the moment the user presses enter. 
 -->



**Why this target:**
<!-- I chose 3.0 seconds because any longer woukd make the system seem slow. We want this system to be able to produce quick and meaningful work without disrupting the workflow of the user. -->


---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 2 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath it, like this:

         ## 1. Retrieved chunks contain the answer

         For at least 4 of my 5 test questions, the retrieved chunks include
         one that contains the answer.

         **Why this target:** ...

         > **Revised in unit 2:** For at least 4 of 5 questions, the top three
         > results contain the answer.
         >
         > **Why revised:** I couldn't judge "the chunks include one that
         > contains the answer" the same way twice — I scored two questions
         > differently on Monday than on Wednesday. The new version is
         > something I can actually check.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "I said 4 of 5 but got 2 of 5, so 2 of 5 is more realistic."

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.

     The whole reason the originals stay visible is so someone can see what you
     said before you knew the answer.
     ───────────────────────────────────────────────────────────────────────── -->
