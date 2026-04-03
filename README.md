# Ultraliskism

> **Demo map** — This map is a demo and showcase for the SC2 editor tooling and Galaxy scripting skills developed at [KimPlaybit/Starcraft-2-Editor-Skills](https://github.com/KimPlaybit/Starcraft-2-Editor-Skills). It serves as a practical reference for how those skills and agent customizations are applied in a real map project.

A cooperative StarCraft II survival map where one or more human players must build a base and hold out against relentless, escalating Zerg attacks. The goal is simple: keep your town hall standing and survive for 27 minutes after the swarm is unleashed.

---

## How It Works

### Phase 1 — Preparation (0:00 – 3:00)

When the game begins, each player spawns with one race-appropriate worker (SCV, Drone, or Probe) and 200 minerals at the map center. A **"Preparation"** countdown timer visible to all players gives you 3 full minutes to gather resources, lay down a base, and get your defenses started before the enemy arrives.

Use this time wisely — there are no enemies yet, but the calm does not last.

### Phase 2 — The Swarm Is Released (3:00)

When the preparation timer expires, the Zerg player (slot 12, computer-controlled) releases its first wave. The moment the Ultralisks spawn, a **"Survive!"** countdown begins — 27 minutes on the clock, counting down to your victory.

The attack comes in two overlapping threads:

#### Ultralisks — Ground Assault

Ultralisks spawn from the map center and escalate over the opening minutes:

| Wave | Time after unleash | Ultralisks spawned |
|------|--------------------|--------------------|
| 1    | Immediately        | 1                  |
| 2    | +1 minute          | 2 more             |
| 3    | +2 minutes         | 4 more             |
| 4    | +3 minutes         | 8 more             |
| 5+   | Every 50 seconds   | 8 per wave (forever) |

After the 4-wave escalation phase, sustained waves of 8 Ultralisks arrive every 50 seconds indefinitely. Every living Ultralisk re-evaluates its target every 10 seconds, constantly hunting the nearest town hall.

#### Mutalisks — Air Harassment

Starting at the **20-minute mark** of the game (roughly 17 minutes into the assault), Mutalisk waves begin striking from the air. Five waves hit at 20, 22, 24, 26, and 28 minutes — each wave dropping **8 Mutalisks** that spawn at random positions spread across the map and immediately hunt player bases. Like Ultralisks, idle Mutalisks retarget every 10 seconds.

---

## Win & Lose Conditions

### You Win if…

The **"Survive!" countdown reaches zero** (27 minutes after the Ultralisks spawn) with your town hall still standing. All surviving players with an intact town hall are granted victory simultaneously.

### You Lose if…

- Your **first town hall is destroyed** by enemy fire. Morphing it (e.g. Hatchery → Lair → Hive, or Command Center → Orbital Command / Planetary Fortress) is safe — the game tracks the morphed form automatically.
- You **lose your last worker** before you have built a town hall. If you haven't secured a base yet, losing your only worker ends the run.

---

## Tips

- **Prioritize your town hall.** It is your only loss condition. Wall it off, surround it with static defenses, and keep units nearby.
- **The first 3 minutes are everything.** Expand your mineral line, build supply, and get at least one defensive structure down before the Ultralisks hit.
- **Ultralisks snowball fast.** The count goes from 1 to 15 in 3 minutes and then 8 more arrive every 50 seconds. If your first line breaks early, the pressure compounds quickly.
- **Watch the clock at 20 minutes.** That is when air harassment begins on top of the Ultralisk flood. Have anti-air ready before the Mutalisks arrive.
