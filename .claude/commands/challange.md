# Challange - Critical Thinking Command

**Purpose:** Encourage thoughtful critical thinking instead of automatic agreement, especially when the user challanges or questions previous assessments.

## Manual Invocation
**Command:** `/challange`
- User explicitly requests critical analysis of a statement or claim
- Wraps the user's statement with critical thinking instructions

## Automatic Invocation (Conservative Triggers)
**MANDATORY AUTOMATIC INVOCATION only when ALL conditions are met:**

1. **Context Requirement:** There is existing conversation context (not an initial question)
2. **Explicit challange Language:** User's message contains explicit disagreement/challange phrases:
   - "That's wrong..." / "That's incorrect..."
   - "I disagree with your..." / "I don't agree that..."
   - "You're wrong about..." / "That's not right..."
   - "Your analysis is flawed..." / "Your assessment is incorrect..."
   - "That doesn't make sense because..." (when followed by contradiction)

**DO NOT AUTO-TRIGGER for:**
- Follow-up questions ("But how do I...?", "Why did you...?")
- Requests for clarification ("I'm confused about...", "Could you explain...?")
- Implementation requests ("Now let's build...", "Based on that research...")
- Feature requests or new topics
- Questions that build on previous responses rather than challange them

## Template

When triggered (manually or automatically), wrap the user's statement with:

---

**CRITICAL REASSESSMENT – Do not automatically agree:**

"$ARGUMENTS"

Carefully evaluate the statement above. Is it accurate, complete, and well-reasoned? Investigate if needed before replying, and stay focused. If you identify flaws, gaps, or misleading points, explain them clearly. Likewise, if you find the reasoning sound, explain why it holds up. Respond with thoughtful analysis—stay to the point and avoid reflexive agreement.

## Instructions for Analysis

1. **Question assumptions** - What underlying beliefs does this statement rely on?
2. **Look for evidence** - What facts support or contradict this claim?
3. **Consider alternatives** - Are there other ways to interpret the situation?
4. **Check for bias** - Could personal, cultural, or ideological bias be influencing this view?
5. **Evaluate completeness** - What important context or nuance might be missing?

Think critically and provide your honest assessment, whether that means agreeing, disagreeing, or finding the truth somewhere in between.

---

## Key Improvements

**Conservative Auto-Triggers:** Only activate on explicit disagreement language, not general follow-up questions.

**Clear Boundaries:** Distinguish between challanges to your reasoning vs. requests for next steps.

**Context Awareness:** Require existing conversation context to prevent triggering on initial questions.

**User Intent Focus:** Preserve the tool's purpose (critical analysis) while avoiding interference with normal workflow progression.