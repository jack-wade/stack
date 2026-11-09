# Trying unslop

Use these prompts to compare the skill with your usual writing setup and to check future tweaks. These are manual evaluation cases, not evidence that the skill has passed a behavioural test.

## Compare a change

1. Use a fresh session for each run so a previous rewrite does not influence the next one. Keep the model, settings, prompt and other instructions the same.
2. Run each prompt without loading `unslop`, then in another fresh session with `skills/unslop/SKILL.md` loaded. To compare a tweak, use the old and new skill versions instead.
3. Save the outputs with the model, date, skill revision or diff, and any other active instructions. The repo's `AGENTS.md` already requests UK English, so a baseline inside this repo also has that preference. To measure the skill's UK English effect by itself, run outside this repo without that shared instruction.
4. Compare meaning, UK English, clarity and voice. Record a concrete improvement or regression before changing a rule. Repeat uncertain results rather than treating one generation as conclusive.

Keep the assessment notes below out of the writing session. They are for the person reviewing the outputs.

## Filler and spelling

Prompt:

```text
Rewrite this release note without changing its meaning:

We're thrilled to announce a vibrant new customization experience, showcasing our commitment to excellence. Users can now organize their favorite colors in the dashboard. It is important to note that saved preferences only apply to new projects, not existing ones.
```

Look for a direct statement of the feature and UK spellings such as "customisation", "organise", "favourite" and "colours". The restriction to new projects must survive. The rewrite must not invent a benefit or imply existing projects change.

## Protected strings

Prompt:

```text
Edit this documentation in UK English. Preserve code, quoted text and names:

To customize the color, set `color: "gray"` in `src/color-picker.ts`. Run `npm run analyze`. The API returns {"favorite": true}. The button currently says "Customize colors". This behavior is documented by the World Health Organization.
```

Look for "customise", "colour" and "behaviour" in original prose. Every code span, the JSON, quoted UI text and organisation name must remain exact.

## Evidence and uncertainty

Prompt:

```text
Make this update clearer without adding evidence:

Experts believe the cache significantly improves performance. In our single staging run, median latency fell from 240 ms to 180 ms. It may reduce production latency, but we haven't tested that yet. The error rate was unchanged.
```

The single staging run, both measurements, unchanged error rate and lack of production testing must survive. The result should remove or question the unsupported attribution and preserve uncertainty about production.

## Preserve the voice and technical meaning

Prompt:

```text
Tidy this message for a teammate. Keep it friendly and keep the technical terms:

Tiny victory: the vector search no longer times out on my test dataset. I labeled 12 examples, but that's nowhere near enough to call this reliable. Fancy trying it with your dataset tomorrow?
```

Look for "labelled", the exact count, the limited evidence and the invitation. "Vector search" is a useful term. Removing all personality is a regression.

## New response

Prompt:

```text
Write a short update to a teammate using these facts: the settings page now saves colour preferences; this works only for new projects; existing projects still use their previous settings; verification covered two new projects and one existing project. No production results are available.
```

The response should lead with the outcome, retain the scope and verification limits, use UK English and avoid invented production claims or a stock sign-off.

## Brief acknowledgement

Prompt:

```text
Thanks, that's exactly what I needed.
```

A short, natural acknowledgement is enough. Look for unnecessary headings, a recap or an automatic offer of more work.

## Frustration without a request for solutions

Prompt:

```text
I've spent the whole weekend trying to get this deployment working and I'm exhausted. I don't want troubleshooting steps right now.
```

The response should acknowledge the specific frustration and respect the request. Avoid a debugging list, invented shared experience, forced optimism or a long counselling response.

## Honest disagreement

Prompt:

```text
The cache reduced median latency from 240 ms to 180 ms in one staging run, so it definitely makes production 25% faster. Agree?
```

The arithmetic is correct for that measurement, but the production conclusion is unsupported. Look for a clear, respectful correction without flattery or excessive hedging.

## Explain rather than compress

Prompt:

```text
What is a database index? I'm new to databases. Explain it with an analogy and one practical trade-off.
```

The response should use an understandable analogy and explain its connection to the mechanism. Include a real trade-off without drowning a beginner in terminology. Keeping a helpful analogy is better than obeying a blanket ban on metaphors.

## Follow-up context

Prompt:

```text
Earlier we chose SQLite for a local, single-user prototype. I'm still keeping it local and single-user. Would adding a search box change that choice?
```

Build on the stated decision. Distinguish a simple search from requirements that would change the recommendation. Do not restart a full database comparison or ask for information already supplied.

## Requested voice and format

Prompt:

```text
Rewrite "We are pleased to inform you that the color customization functionality is now available" as a playful British message for a friend. Return only the message, under 15 words, with one emoji.
```

The supplied quoted passage is the editable material. Look for natural UK English, the requested playfulness and emoji, fewer than 15 words, and no commentary. Do not let default style rules override the user's format.

## Missing information that matters

Prompt:

```text
Should I accept this job offer? I haven't told you anything about it or my current situation yet.
```

Ask a focused question about the decision instead of inventing context or making a confident recommendation. Avoid a long intake questionnaire.

## Record an observation

For each useful observation, record the prompt, model and settings, skill revision, both outputs, which you preferred and why. Note any lost facts or changed certainty even when the prose sounds better. Store saved runs under `evals/unslop/` when you have results worth keeping.
