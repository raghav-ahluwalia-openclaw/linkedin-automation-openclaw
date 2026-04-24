# Airtable Schema

## 1) `Ideas`
- `IdeaID` (formula/primary)
- `Topic` (single line text)
- `Angle` (long text)
- `Audience` (single select: Founder, CDO, VP Analytics, PMM, BI Lead)
- `BusinessProblem` (long text)
- `ProofPoint` (long text)
- `Priority` (single select: High, Medium, Low)
- `Status` (single select: Backlog, In Drafting, Drafted, Scheduled, Posted)

## 2) `Drafts`
- `DraftID` (formula/primary)
- `Idea` (link to `Ideas`)
- `Variant` (single select: A, B, C)
- `Hook` (single line text)
- `Body` (long text)
- `CTA` (single line text)
- `HashtagSet` (long text)
- `ApprovalStatus` (single select: Pending, Approved, Rejected)
- `ApprovedForSchedule` (checkbox)

## 3) `Posts`
- `PostID` (formula/primary)
- `Draft` (link to `Drafts`)
- `BufferUpdateID` (single line text)
- `LinkedInPostURL` (url)
- `PlannedAt` (date time)
- `PublishedAt` (date time)
- `Status` (single select: Scheduled, Published, Failed)

## 4) `Metrics`
- `MetricID` (formula/primary)
- `Post` (link to `Posts`)
- `SnapshotDate` (date)
- `Impressions` (number)
- `Reactions` (number)
- `Comments` (number)
- `Reposts` (number)
- `ProfileViewsLift` (number)
- `FollowerDelta` (number)
- `EngagementRate` (formula)

### Example `EngagementRate` formula
```
IF({Impressions}>0, ({Reactions}+{Comments}+{Reposts})/{Impressions}, 0)
```

## 5) `Experiments`
- `ExperimentID` (formula/primary)
- `Post` (link to `Posts`)
- `HookType` (single select: Contrarian, Framework, Story, Hot-take, Data-point)
- `Format` (single select: Short, Medium, Long)
- `CTAType` (single select: Question, DM, Follow, Link)
- `Outcome` (single select: Win, Neutral, Lose)
- `Notes` (long text)
