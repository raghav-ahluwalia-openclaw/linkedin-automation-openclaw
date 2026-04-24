# Prompt Library

## 1) Generate 3 opinion-piece variants

Use this prompt with variables from your `Ideas` table:

```text
You are writing LinkedIn opinion pieces for a senior analytics leader.
Topic: {{Topic}}
Angle: {{Angle}}
Audience: {{Audience}}
Business problem: {{BusinessProblem}}
Proof point: {{ProofPoint}}

Output 3 variants (A/B/C), each with:
1) Hook (max 18 words)
2) Body (120-220 words)
3) CTA (single sentence)
4) 5 relevant hashtags

Constraints:
- Style: sharp, practical, no fluff
- Focus on data analytics + business intelligence outcomes
- Include one clear business impact statement
- Avoid emojis and hype language
- No invented stats
Return valid JSON with keys: variants[].hook, body, cta, hashtags[]
```

## 2) Rewrite to your voice

```text
Rewrite this draft in my voice: direct, contrarian-but-practical, leadership tone.
Keep meaning intact. Improve clarity and punch.
Limit to 180 words.
Draft: {{DraftBody}}
```

## 3) Weekly performance analyst prompt

```text
You are a growth analyst for LinkedIn thought leadership.
Given post performance data (impressions, comments, reposts, engagement rate, follower delta), do:
1) Rank top 3 posts and explain why they won
2) Identify bottom 3 and why they underperformed
3) Extract winning hook patterns, topic clusters, and CTA styles
4) Recommend 7 new post ideas for next week
5) Propose 2 experiments (hook or format A/B)

Return concise bullets and a one-week action plan.
Data:
{{MetricsJSON}}
```
