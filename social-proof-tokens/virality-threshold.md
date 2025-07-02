---
icon: fire
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Virality Threshold

The virality threshold system determines when content and creators become eligible for Social Proof Token creation. This automated system uses weighted scoring algorithms to monitor engagement and ensure only content with genuine community interest can launch tokens.

## How Virality Detection Works

Engagement is continuously tracked using a scoring system that values different types of interactions.

**For Post Tokens:**
- Viral Score = (Likes × 1) + (Comments × 3) + (Tips × 10)
- Threshold = 100 points

**For Profile Tokens:**
- Viral Score = (Followers × 1) + (Posts × 1) + (Tips × 5)
- Threshold = 100 points

**Default Weights (governance adjustable):**
- Likes: 1
- Comments: 3
- Tips: 10 (posts), 5 (profiles)
- Viral Threshold: 100 points

When content crosses the viral threshold:
1. Eligibility achieved: content becomes eligible for token auction
2. Creator notification: owner receives notification
3. Manual initiation: creator must manually start the auction process
4. Public visibility: eligible content may be highlighted for community awareness

## Quality Assurance Features

Anti-gaming mechanisms include:
- Tips require actual MySo token transfers (cannot be faked)
- Comments and reactions tracked through verified user interactions
- Follower counts based on authenticated profile connections
- Blocked users' engagement does not count toward viral scores
- Rate limiting to prevent artificial spikes
- Transparent, public scoring formulas

## Eligibility Examples

**Post Token Scenarios:**
- 50 likes + 10 comments + 2 MySo tips = 50 + 30 + 20 = 100 points ✅
- 20 likes + 25 comments + 1 MySo tip = 20 + 75 + 10 = 105 points ✅
- 10 likes + 5 comments + 8 MySo tips = 10 + 15 + 80 = 105 points ✅
- 30 likes + 5 comments + 0 tips = 30 + 15 + 0 = 45 points ❌

**Profile Token Scenarios:**
- 80 followers + 15 posts + 2 MySo tips = 80 + 15 + 10 = 105 points ✅
- 50 followers + 10 posts + 8 MySo tips = 50 + 10 + 40 = 100 points ✅
- 90 followers + 8 posts + 0 tips = 90 + 8 + 0 = 98 points ❌

## Strategic Implications

For creators, the system rewards genuine engagement and community building. For the community, viral threshold crossing signals proven interest and potential value. Platforms benefit from quality token launches and ecosystem health. The virality threshold system maintains high standards and provides clear, achievable goals for creators.

*Emergency trading controls may be activated by governance in exceptional circumstances.* 