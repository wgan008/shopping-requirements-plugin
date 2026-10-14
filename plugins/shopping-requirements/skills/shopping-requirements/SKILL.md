---
name: shopping-requirements
description: Turn a big-ticket purchase (appliance or furniture — sofa, washing machine, fridge, bed frame, mattress, wardrobe, air conditioner, etc.) into a clear, benchmarked requirements list ready to paste into a shopping platform's AI assistant (淘宝问一问/京东AI导购 etc). Use whenever the user is shopping for furniture/appliances and wants help figuring out what actually matters, or asks to "写一个购物需求单" / "generate shopping requirements" / "help me buy a [product]".
---

Produce a requirements list for a furniture/appliance purchase by working through four
steps in order. Do not skip to the output — each step's result feeds the next, and skipping
straight to "what do you want" produces a vague wish list instead of a benchmarked spec.

## Step 1 — Identify the make-or-break criteria for this product category

Ask: what is the failure mode that ruins this product, and what is the core function it
must deliver? For a sofa, cheap foam means it collapses within a year — durability is
make-or-break. For a fridge, a noisy compressor next to an open-plan kitchen ruins daily
life — noise is make-or-break there in a way it isn't for a washing machine tucked in a
utility room.

Check `references/furniture.md` and `references/appliances.md` first — they already cover
sofa, bed frame, mattress, wardrobe/wardrobe cabinets, dining table, washing machine,
refrigerator, air conditioner, water heater, cooling fan, dishwasher, and coffee machine
with pre-researched criteria, metrics, and benchmarks (including relevant China national
standards). If the product isn't in either file, derive criteria yourself using the same
failure-mode method, and keep the reasoning one line per criterion — don't pad with
criteria that don't actually differentiate good from bad units.

Typical criteria worth checking for *any* category, on top of the category-specific ones:
- Structural/material durability
- The specific China national/industry standard that applies (energy label, formaldehyde
  emission grade, abrasion rating, etc.) — cite it by name/grade, not "good quality"
- Fit: physical dimensions against the space, doorway, elevator, hallway the item must pass
  through to be delivered and installed
- Health/safety: material off-gassing (甲醛/VOC) for anything with board, foam, or paint

## Step 2 — Convert each criterion into a measurable metric

A criterion like "durability" is not actionable until it becomes a spec-sheet number:
foam density in D, motor type + warranty years, abrasion rating in Martindale rubs,
formaldehyde grade (E0/E1), decibel rating, energy label tier. If a criterion can't be
reduced to a number, standard grade, or yes/no spec that a listing or seller can answer,
it isn't specific enough yet — tighten it.

## Step 3 — Set the benchmark/threshold for each metric

For each metric, state the minimum acceptable value (below which the product is
unqualified/avoid) and, where useful, the range that separates "acceptable" from "good"
from "great". Use the benchmarks in the reference files as the default; only deviate if the
user gives a reason to (e.g. heavier household member → higher weight rating needed).
Always give the threshold as a number + unit, not a qualitative word.

## Step 4 — Fold in the user's personal constraints

Ask for (or use what's already been given in conversation):
- **Space**: exact dimensions that matter (length/width/height/clearance), ideally with a
  few cm of safety margin below the hard limit, not the exact limit itself
- **Budget** ceiling
- **Style/color**, matched to the room's existing style
- **Household specifics**: number of people, anyone with mobility issues, water/power
  supply constraints, delivery access (stairs vs elevator, doorway width)
- Any other explicit must-haves or dealbreakers the user has mentioned

If any of these are missing and the user hasn't supplied them earlier in the conversation,
ask before producing the final list — a requirements list with a placeholder budget or no
dimensions isn't useful to paste anywhere.

## Output

Write the final list in **Chinese**, formatted so it can be pasted directly into a shopping
platform's AI assistant chat box. Structure:

```
我想买一个[产品类别],以下是我的要求:

【硬性指标,必须满足】
1. [标准名称/指标]:[数值+单位],低于/高于此不考虑。(一句话说明原因,可省略)
2. ...

【个人偏好】
1. 尺寸:...
2. 预算:...
3. 风格/颜色:...
4. 其他:...

请根据以上要求推荐几款符合条件的产品,并逐条说明每款产品是否满足上面的硬性指标。
```

Keep 硬性指标 items to numbers/grades/standards only — no adjectives. Keep the whole list
scannable; a shopping AI assistant handles a tight spec far better than a long paragraph.
