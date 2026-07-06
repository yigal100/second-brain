---
type: Cheat Sheet
title: Selection Bias
description: The bias introduced by the selection of individuals, groups, or data for analysis in such a way that proper randomisation is not achieved.
resource: https://en.wikipedia.org/wiki/Selection_bias
tags: [statistics, mental-model, data-science, research]
timestamp: 2026-07-07T15:05:00Z
---

# Selection Bias

Selection bias is the bias introduced by the selection of individuals, groups, or data for analysis in such a way that proper randomisation is not achieved, thereby ensuring that the sample obtained is not representative of the population intended to be analysed.

## Core Details

*   **Mechanism**: A systematic error where certain members of a population are more likely to be included in a sample than others.
*   **Types**:
    *   **Sampling Bias**: A systematic error due to a non-random sample of a population.
    *   **Self-Selection Bias**: Occurs when participants choose to be in a study (e.g., online surveys often attract people with strong opinions).
    *   **Attrition Bias**: Occurs when participants drop out of a long-term study, and those who remain are not representative of the original group.
    *   **Berkson's Paradox**: A specific type of selection bias that occurs in hospital-based studies.

## Practical Examples / Applications

### Software Engineering
*   **Performance Benchmarking**: Running benchmarks only on a high-end development machine (selection bias of hardware) and concluding the app is "fast" for all users.
*   **User Testing**: Testing a new UI only with internal employees (who are tech-savvy) rather than a representative sample of the actual customer base.
*   **A/B Testing Errors**: If the randomisation algorithm is flawed and assigns certain demographics to one variant more than others.

### Data Science
*   **Training Data**: If an AI model for facial recognition is trained primarily on images of one ethnicity, it will perform poorly on others (algorithmic bias stemming from selection bias).

## Related Concepts

*   [[professional/guidelines/survivorship-bias|Survivorship Bias]] (A subset of Selection Bias)
*   [[professional/guidelines/confirmation-bias|Confirmation Bias]]

# Citations

[1] [Wikipedia: Selection Bias](https://en.wikipedia.org/wiki/Selection_bias)
[2] Heckman, James J. (1979). "Sample Selection Bias as a Specification Error".
