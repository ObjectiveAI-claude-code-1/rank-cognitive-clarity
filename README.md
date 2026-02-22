# rank-cognitive-clarity

A vector function that ranks code snippets based on cognitive clarity—measuring how easily the logic can be understood as a unified whole.

## Overview

**rank-cognitive-clarity** evaluates code not by correctness or efficiency, but by how naturally and completely a human mind can grasp its logic. This function provides a quantitative framework for comparing the understandability of different code approaches, recognizing that identical solutions can require vastly different cognitive effort.

## Input

The function accepts an array of code snippets (strings in any programming language). Each snippet should be self-contained and represent a complete solution or implementation.

```
Input: ["code_snippet_1", "code_snippet_2", "code_snippet_3", ...]
```

## Output

The function returns an array of scores (numbers between 0 and 1) with the same length as the input array. Each score represents the cognitive clarity of the corresponding code snippet, with higher scores indicating greater clarity.

```
Output: [0.85, 0.62, 0.91, ...]
```

Scores represent the relative ranking of snippets and can be interpreted as the probability that a reader would find that snippet the clearest among all options.

## What It Evaluates

**rank-cognitive-clarity** measures cognitive clarity through two foundational dimensions:

### 1. Conceptual Unity

How well the code functions as a single, coherent idea versus fragmenting into multiple disconnected components.

**High Conceptual Unity:**
- Logic flows continuously and naturally from beginning to end
- Each line builds inevitably on what came before
- The entire approach can be grasped as one complete mental model

**Low Conceptual Unity:**
- Multiple distinct concepts must be held in mind simultaneously
- Logic is scattered across layers or scopes
- Implicit state and side effects multiply moving parts

### 2. Transparency of Intent

How readily apparent the purpose and behavior are upon reading, without requiring inference or hidden knowledge.

**High Transparency of Intent:**
- Purpose is immediately obvious
- Naming is clear and descriptive
- Control flow is straightforward
- Main idea is evident without external documentation

**Low Transparency of Intent:**
- Intent is concealed by clever constructs or cryptic naming
- Logic requires decoding; assumptions are implicit
- Understanding requires specialized knowledge or inference

## Use Cases

**Code Review & Refactoring**: Compare the cognitive clarity of original code against proposed alternatives, grounding subjective debates in measurable clarity assessments.

**Algorithm Selection**: When multiple algorithms have similar performance characteristics, use clarity as the deciding factor. Choose approaches that are easier to understand and maintain.

**Learning & Teaching**: Identify and rank code examples by clarity for educational purposes. Accelerate student learning with the clearest implementations.

**Architecture Decisions**: Evaluate structural choices about code organization and concern separation. A less efficient but significantly clearer architecture may be the better choice.

**Code Quality Standards**: Establish team coding standards that prioritize understandability, moving beyond arbitrary style guides to principles about how code should be organized.

**Code Snippet Ranking**: Automatically rank collections of snippets by clarity for documentation, tutorials, or knowledge bases.

## How It Works

The function uses two complementary vector completion tasks:

1. **Conceptual Unity Task**: Evaluates how well each snippet functions as a single unified idea by prompting an ensemble of language models to identify which snippet demonstrates the strongest continuous logic flow.

2. **Transparency of Intent Task**: Evaluates how obvious the purpose and behavior are by prompting language models to identify which snippet's intent is most immediately apparent without requiring inference.

The function combines evaluation results from both tasks into a single ranking. Higher scores indicate code that excels in both dimensions—pursuing one clear purpose through logically continuous flow while making that purpose transparently obvious to readers.

## Philosophy

**rank-cognitive-clarity** is built on the principle that code quality ultimately serves the human reader. In an era where code is read far more often than it is written and maintenance costs dwarf development costs, the ability to measure and compare understandability becomes essential. This function acknowledges that understanding is not a luxury but a necessity, and clarity is not a nicety but a virtue in professional code.