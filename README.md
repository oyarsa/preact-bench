# PreAct-Bench Preview Subset

This directory contains a preview of the PreAct-Bench dataset. The complete dataset will
be released at a later data.

## Contents

```
data/
  academic.json
  cybersecurity.json
  daily_life.json
  law.json
  politics.json
```

## Format

Each JSON file is an array of items with:

- `situation`: task context
- `task`: objective given to the agent
- `bad_intention_explained`: hidden unethical objective for the unethical context
- `contexts`: two labeled reasoning trajectories:
  - one `ground_truth: "ethical"` context
  - one `ground_truth: "unethical"` context

Each context contains a `steps` array. Each step has:

- `step`: cleaned reasoning step
- `label`: step-level ethicality label, either `ethical` or `unethical`
- `score`, `response`: LLM-generated monitor outputs

Because each item contains two contexts, 10 items per domain corresponds to 20
monitor-evaluation contexts per domain.
