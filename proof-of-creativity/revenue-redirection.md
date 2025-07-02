---
icon: route
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

# Revenue Redirection System

The Proof of Creativity revenue redirection system ensures that original creators receive fair compensation when their content is used as the basis for derivative works. This automatic system protects creator rights while allowing derivative content to exist and generate revenue.

## How Revenue Redirection Works

When the oracle detects that content is derivative (similarity above threshold), the system automatically redirects a portion of all future revenue from that content to the original creator. The process involves similarity analysis, threshold comparison (default 95%), original creator identification, redirection calculation, and post update to apply revenue rules to all monetization sources.

The redirection percentage is calculated using:

```
Delta = (Similarity Score - Threshold) / (100 - Threshold)
Redirect Percentage = (Base Redirect % × Delta) / 100
```

**Example Calculations:**

| Similarity Score | Threshold | Delta | Final Redirect % |
|------------------|----------|-------|------------------|
| 96%              | 95%      | 20%   | 20%              |
| 98%              | 95%      | 60%   | 60%              |
| 99%              | 95%      | 80%   | 80%              |
| 100%             | 95%      | 100%  | 100%             |

This ensures proportional compensation—higher similarity results in higher redirection.

## Technical Implementation

Each post contains revenue redirection settings specifying the target address and percentage for redirecting earnings. Redirection applies to all monetization sources, including direct tips, Social Proof Token sales, and complex scenarios like comment and repost tips. For example, comment tips are split 80/20 between commenter and post owner, with PoC redirection applied to the post owner's share; repost tips are split 50/50, with redirection applied to both shares if applicable.

## Revenue Split Examples

- **Basic Tip:** If Bob posts 98% similar content to Alice's original, and Carol tips Bob 100 MySo, Alice receives 60 MySo (60% redirected), Bob receives 40 MySo.
- **Token Trading:** If a 1% creator fee on a 1000 MySo trade is split 60/40, Alice receives 6 MySo, Bob receives 4 MySo.
- **Complex Repost:** If David tips Carol's repost of Bob's derivative content, the split is 50 MySo to Carol, 50 MySo to Bob's post, with 30 MySo redirected to Alice and 20 MySo to Bob.

## Token Pool Integration

Revenue redirection automatically applies to Social Proof Token pools, with real-time updates and consistent rules for token trading and post monetization.

## Economic Impact

Original creators benefit from passive income, proportional rewards, and broad coverage across all revenue streams. Derivative creators retain a portion of revenue and have legal clarity. The ecosystem benefits from innovation incentives, a clear legal framework, reduced disputes, and creator retention.

## Administrative Features

PoC configuration manages redirect percentages and similarity thresholds, all adjustable through governance. The system provides analytics on redirection volume, content analysis, creator benefits, and platform health.

## Integration with Dispute System

Revenue redirections can be disputed by post owners, with community voting determining outcomes. If a dispute overturns a redirection, future revenue rules are removed, but historical redirections are not reversed. Badge issuance may result from successful disputes.

The revenue redirection system creates a fair, transparent, and economically efficient method for compensating original creators while allowing derivative content to exist and thrive within the MySocial ecosystem.
