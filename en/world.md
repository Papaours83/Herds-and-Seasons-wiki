# The world

[Home](../README.md) · [Guide](guide.md) · [Animals](animals.md) · [Machines and items](machines.md) · **The world** · [Recipes](recipes.md)

## Seasons

There are four seasons of 7 days each, and you can change that length. They don't change how the world looks: they matter for temperature, breeding and grazing.

| Season | Temperature change |
|---|---|
| Spring | 0 °C |
| Summer | +8 °C |
| Autumn | -1 °C |
| Winter | -10 °C |

`/time set` doesn't change the season, and sleeping moves the calendar forward.

## Temperature

The temperature of a spot is worked out like this:

- the biome: about 16 °C on plains, 38 °C in desert and 2 °C in tundra
- the season, from the table above
- the time of day: 3 °C more at noon and 4 °C less at midnight
- altitude: above layer 80, 0.08 °C less per block
- shelter: with no sky above, the temperature moves towards 15 °C
- hot or cold blocks within 6 blocks and 4 blocks up or down

Each source gives its full power when touching, then less and less with distance. Sources add up, to +60 °C and -25 °C at most.

| Source | Power | Range (blocks) |
|---|---|---|
| Lava, lava cauldron | +30 °C | 6 |
| Fire | +20 °C | 4 |
| Lit campfire | +16 °C | 5 |
| Lit soul campfire | +11 °C | 5 |
| Lit furnace, smoker or blast furnace | +8 °C | 3 |
| Magma block | +8 °C | 3 |
| Torch | +3 °C | 2 |
| Lantern | +2 °C | 2 |
| Blue ice | -12 °C | 4 |
| Packed ice | -8 °C | 3 |
| Ice | -6 °C | 3 |
| Snow block, powder snow | -4 °C | 2 |

## Crops

A crop only grows inside its temperature range. So in winter, a heated greenhouse can be necessary.

| Crop | Growing range |
|---|---|
| Wheat | 4 to 32 °C |
| Carrots | 2 to 28 °C |
| Potatoes | 4 to 28 °C |
| Beetroots | 0 to 28 °C |
| Melon | 12 to 38 °C |
| Pumpkin | 10 to 36 °C |
| Sweet berries | 0 to 30 °C |
| Cocoa | 18 to 40 °C |
| Torchflower, pitcher plant | 10 to 32 °C |
| Other crops | 2 to 35 °C |

## Soil fatigue

Harvesting the same crop in the same spot wears out the farmland, starting with the 3rd harvest in a row. Fatigue goes from 0 to 5. Each point takes away 15% of the harvest and gives a 15% chance that the plant won't grow when it should.

Harvesting a different crop starts the count again from 1. Bone meal takes 1 harvest off the count.

## Wild populations

Each species has a population across the whole world, given in [the species table](animals.md). The 17 tracked plants start at 300: small flowers, the sweet berry bush and brown and red mushrooms.

A population drops by 1 when a player kills a wild, captured or released animal, and when a wild plant is broken. A plant placed by a player doesn't count, and neither does a farm animal. A species regains 2% of its maximum per day passed, unless it's extinct.

| Status | Population |
|---|---|
| Common | Over 50% of the maximum |
| Vulnerable | 50% or less |
| Endangered | 25% or less |
| Extinct in the wild | 0 |

An extinct species no longer appears naturally, and an extinct plant is no longer on the surface in new chunks. To save it:

- release a farm animal with the [journal](machines.md): +3 the first time
- use a [seed bank](machines.md): the species returns at 10% of its maximum

## Pens in detail

A pen is measured once a minute for the animals living in it, and every 2 minutes for a free animal. If a measurement reaches an unloaded chunk, it concludes nothing and nothing changes.

Gates, doors and trapdoors count according to their real state, even when redstone changes them. Above 16,384 blocks, the area counts as open.

## Settings

In `config/faunaflora-common.toml`:

| Setting | Default | Limits |
|---|---|---|
| `seasonLengthDays` | 7 | 1 to 120 |
| `wildRegrowthPerDay` | 0.02 | 0 to 1 |

## Commands

They're for operators (level 2) and are mostly meant for testing. The jar still contains these test tools.

| Command | Effect |
|---|---|
| `/faunaflora info [target]` | Full report on an animal |
| `/faunaflora pen [target]` | An animal's area: pen, surface, facilities |
| `/faunaflora housing` | Pens in memory and measurement cost |
| `/faunaflora clock` | Time, day, season, nights slept |
| `/faunaflora calendar set <day>` | Changes the calendar day |
| `/faunaflora calendar season <season>` | Changes the season |
| `/faunaflora needs <targets> <food> <water>` | Sets needs |
| `/faunaflora status <targets> <origin> <status>` | Sets origin and status |
| `/faunaflora spawn <species> male\|female` | Spawns an animal |
| `/faunaflora population [species] [value]` | Reads or sets a population |
| `/faunaflora population plant <plant> [value]` | Same for a plant |
| `/faunaflora testfarm` | Builds a demonstration farm |
