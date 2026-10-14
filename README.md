# shopping-requirements

A Claude plugin that turns a big-ticket furniture or appliance purchase into a clear, benchmarked requirements list, written in Chinese and ready to paste into a shopping platform's AI assistant (淘宝问一问, 京东AI导购, etc.).

把大件家具/家电的购买需求，变成一份带量化指标和国标依据的需求单，可直接粘贴给淘宝问一问、京东AI导购等购物助手。

## What it does

Claude works through four steps instead of jumping to a vague wish list:

1. **Make-or-break criteria** – identifies the failure modes that ruin this product category (e.g. low-density foam in a sofa, a noisy compressor in a fridge).
2. **Measurable metrics** – converts each criterion into a spec-sheet number, grade or standard (foam density in D, Martindale rubs, E0/E1 formaldehyde grade, energy label tier, dB).
3. **Benchmarks** – sets the minimum acceptable value and the acceptable / good / great ranges.
4. **Personal constraints** – folds in your space dimensions, budget, style, household and delivery access, and asks for anything missing.

Built-in reference benchmarks cover: sofa, bed frame, mattress, wardrobe, dining table, washing machine, refrigerator, air conditioner, water heater, cooling fan, dishwasher and coffee machine. Other categories are derived with the same method.

## Install

**Claude Code**

```
/plugin marketplace add wgan008/shopping-requirements-plugin
/plugin install shopping-requirements@vera-plugins
```

**Claude desktop / Cowork**: download `shopping-requirements.plugin` from the [Releases](https://github.com/wgan008/shopping-requirements-plugin/releases) page and open it, or add this repo as a plugin marketplace.

**Skill only (claude.ai)**: zip the `plugins/shopping-requirements/skills/shopping-requirements` folder and upload it under Settings → Capabilities → Skills.

## Usage

Just ask, in English or Chinese:

- "Help me buy a sofa for my living room"
- "帮我写一个洗衣机的购物需求单"
- "Generate shopping requirements for a 2-door fridge, budget ¥5000"

## Repo layout

```
.claude-plugin/marketplace.json          # marketplace manifest (lets others add this repo)
plugins/shopping-requirements/
├── .claude-plugin/plugin.json           # plugin manifest
└── skills/shopping-requirements/
    ├── SKILL.md
    └── references/
        ├── furniture.md
        └── appliances.md
```

## Contributing

Benchmarks for new categories are welcome: add a section to `references/furniture.md` or `references/appliances.md` in the format *criterion → metric → benchmark (unqualified / acceptable / good)*, citing the relevant national standard where one applies.

## License

MIT
