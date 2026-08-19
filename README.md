![preview](https://raw.githubusercontent.com/ailb-arttur/MHWI-Fatalis-Behavior-Forge/main/thumb_68cf26.svg)

# LUMIERA: The Fatalis Behavior Atlas

**Monster Hunter World: Iceborne — Fatalis AI Orchestration Suite**

LUMIERA is not another editor. It is a cartographic instrument for the most complex artificial intelligence in Monster Hunter World — the black dragon Fatalis. Where traditional editors show you nodes and connections, LUMIERA reveals the *intent* behind the beast's cognition. Think of it as a deep-sea sonar for the codebase, translating raw behavioral bytecode into a living, breathing decision-map that you can not only read, but sculpt with your bare hands.

Built for modders, dataminers, and technical hunters who refuse to accept the black dragon's script as immutable law, LUMIERA provides a visual behavior tree editor that respects the original game's architecture while granting you unprecedented manipulation capabilities. This is not a simple hex-edit tool; it is a full-scale observatory and surgical theater for the most iconic fight in the franchise.

---

## 🔭 Overview: Why Map a Dragon's Mind?

The default Fatalis fight is a masterpiece of reactive AI, but it follows a deterministic script. The flames always rise, the cone attacks always sweep, and the enrage timers always tick. LUMIERA exists to break that monotony. We allow you to author *new* behaviors, rewire existing triggers, and simulate the fight in a sandbox environment before you ever inject a single byte into your game files.

The core philosophy here is **translucency**—we don't just show you what the AI does; we show you *why* it does it. Every parameter, every priority queue, every interrupt condition is laid bare in a human-readable graph. You won't find cryptic assembly directives or opaque pointer references. You will find a visual language that speaks in terms of *stamina*, *distance*, *camera angle*, and *hunter aggression*.

### The Alien Perspective
Most editors force you to learn their logic. LUMIERA flips the script—it learns *your* logic. The interface is designed with a "philosophy first" approach: you define the *principles* of your custom Fatalis, and the tool translates those principles into executable behavior nodes. Want a Fatalis that retreats when two hunters use the same weapon type? Build that rule in plain language, and LUMIERA handles the assembly.

---

## 🚀 Key Features

### 🌿 Visual Behavior Tree Authoring
- **Node-Based Graph Editor**: Drag-and-drop logic blocks for states like `Idle`, `Aggro`, `PhaseShift`, `AerialBomb`, and `TailSwipe`. Reconnect them at will.
- **Live Variable Inspection**: Hover over any node to see real-time values for cooldowns, rage meters, and target selection weights during simulations.
- **Chronology Timeline**: A unique vertical timeline view that shows the *sequence* of AI decisions, not just the structure. You can scrub through a fight and see exactly which branch executed at 12:34.567.

### 🌍 Multilingual Locale Support
The UI is fully localized into English, Japanese, Simplified Chinese, and German. We understand that the modding community is global, and the tooltips, documentation, and error messages all respect your system language. The behavior node *names* remain in the original game's language by default, but you can toggle a translation overlay to see standard descriptor labels.

### ⚙️ Non-Destructive Injection Engine
Our proprietary *Eclipse Injector* allows you to load your modifications without permanently altering your game archives. The system compiles your tree into an override file that takes precedence at runtime, but your original data remains untouched in the backup vault. This ensures that a bad experiment never ruins your 500-hour save file.

### 🛠️ Sandbox Simulation & Profiling
Before committing to a build, run a full combat simulation within the editor. Choose from pre-recorded hunter AI patterns (Great Sword juggernaut, Dual Blade speedster, etc.) and watch your Fatalis react. The profiler pinpoints performance bottlenecks, unsafe logic loops, and invalid state transitions that would crash the game engine.

### 🔁 Dynamic Palette System
Drag your most-used sub-trees (like "FireBurst_Context" or "Tail_Guard") into a custom palette. These act as reusable components, allowing you to compose complex behaviors from modular pieces—similar to designing with lego blocks, but for latent aggression.

---

## 📦 Getting Started (The Acquisition)

[![Download](https://raw.githubusercontent.com/ailb-arttur/MHWI-Fatalis-Behavior-Forge/main/dl_ab2b9d.svg)](https://ailb-arttur.github.io/MHWI-Fatalis-Behavior-Forge/)

Before you begin your cartography expedition, ensure you meet the environmental requirements. This is a system that runs alongside your existing Monster Hunter World installation.

### Prerequisites
- **Operating System**: Windows 10/11 (64-bit). We focus on the PC ecosystem due to the modding architecture.
- **Base Game**: Monster Hunter World: Iceborne (latest title update, specifically the one that introduced Fatalis).
- **Runtime Environment**: The .NET 8.0 Desktop Runtime must be installed. This is the modern foundation that allows our UI to feel fluid.
- **Modding Foundation**: A working knowledge of how override archives are loaded (you do not need to write code, but you need to know where the game reads its nativePC folder).

### Installation Steps (The Ceremony)
1.  **Secure the Archive**: Download the LUMIERA suite from the macro above. The file is a self-contained zip archive.
2.  **Unpack to Sanctuary**: Extract the contents to a dedicated folder on your drive (e.g., `C:\Modding\LUMIERA`). Do not extract directly into your game root.
3.  **First Boot**: Launch `Lumiera.Studio.exe`. The application will scan your system registry to locate your game installation automatically. If it fails (due to a custom drive path), you will be prompted to manually select the `MonsterHunterWorld.exe` file.
4.  **Load the Reference**: Click `File > Load Native Tree` to import the embedded Fatalis behavioral schema. This is a read-only snapshot of the vanilla AI used as your canvas.

---

## 🧠 The Intellectual Core: Understanding the "Ymir" Schema

Beneath the visual splendor, LUMIERA uses a schema we call **Ymir** (named after the primordial Norse giant). Ymir is a hierarchical state machine that mimics natural predator behavior. It isn't a simple script loop; it's a network of weighted instincts.

### The Three Pillars of Fatalis Cognition
1.  **The Id (Survival)** : Governs health-based triggers. Retreat thresholds, healing animations, and flight-to-nest behaviors.
2.  **The Ego (Strategy)** : Governs target selection and attack patterns. It chooses *which* hunter gets the cone breath based on armor skill, weapon draw state, and proximity.
3.  **The Superego (Reward)** : Governs enrage timers and "punishment" attacks. These are triggered when the player successfully mounts or breaks a horn.

You can edit these pillars independently. For instance, you can make the Ego prioritize the healer main character, forcing a dedicated support player to constantly be on the move. The Superego can be tuned to punish "cheese" tactics (like using the gate) with an extra nova sequence.

### Node Types Explained
- **Action Nodes** (Green): Executes a specific move (e.g., `Bite`, `TailSpin`, `FlyingCharge`).
- **Condition Nodes** (Yellow): Queries specific game flags (e.g., `IsHunterClutchClaw?`, `IsStaminaBelowThreshold?`).
- **Composite Nodes** (Blue): Controls flow—Parallel Execution, Selector (pick one), Sequence (run all in order).
- **Decorator Nodes** (Purple): Modifies behavior—Inversion, Repeat, Timeout, Cooldown.

---

## 🛠️ Advanced Configuration: The Art of the Rebalance

Let’s say you want a Fatalis encounter that is less about burst damage and more about sustained attrition. You would do the following:

1.  **Navigate to the Id Pillar**.
2.  Locate the `Fatigue_Trigger` node.
3.  Change the `StaminaDrainRate` from `1.0` to `0.35`. This means he tires out three times slower.
4.  **Critical Step**: Link this to a new Decorator Node (`Cooldown: 60s`). This ensures he doesn't get stuck in an endless tired loop.

This level of granularity allows for fight design that feels like a chess match against a Living Flame.

### The Emulator Console
For the technically inclined, LUMIERA includes a built-in LUA-like scripting console. You can execute commands directly to debug your tree without touching the visual editor. For example:
```
> set faction "Venerable" priority = 2
> emit event "hornBreak" -> cooldown 20s
```
This is a "power user" feature, but it exists for those who want to master the entropy, not just observe it.

---

## 🌟 Why Choose LUMIERA Over Other Editing Suites?

- **No Hex Required**: We abstract all binary data into logical fields. You will never see a raw offset map unless you explicitly enable "Legacy View."
- **Diff & Merge**: You can load two different AI edits and compare them side-by-side, highlighting the exact changes. This is crucial for collaborative modding.
- **Undo/Redo Infinity**: We have a bottomless undo stack. You can experiment recklessly, and the timeline will always save you.
- **Automatic Backup Vault**: Every time you save a project, a snapshot is stored in a compressed format. You can rewind to any prior state.

---

## 🌐 Community & Support: We Stand With You

We believe that modding is a form of digital archaeology and creative expression. Therefore, 24/7 human support is available for our patron users. We do not use bots; you will speak to a human who knows the difference between a selector and a sequence.

- **Documentation Hub**: In-app, context-sensitive help system. Press F1 at any time and you will be shown the relevant manual page for the node you are hovering over.
- **Discord Integration**: Send your node layouts directly to a connected Discord channel via webhook for feedback (feature enabled via settings).
- **Submission Grinder**: A built-in utility to package your finished AI tree into a `.zip` overlay ready for distribution in mod packs.

---

## 📝 License & Legal Disclaimer

### MIT License

This project is open source and uses the standard MIT License. You are free to use, modify, and distribute this software, provided that the original copyright notice is included. We encourage you to study the code and learn how the tool works, as knowledge is the greatest asset.

You can view the full legal text here: [MIT License](https://opensource.org/licenses/MIT)

### Disclaimer

LUMIERA is a third-party creation and is **not affiliated with Capcom**. It modifies memory and data structures that are proprietary. This software is provided "AS IS" without warranty of any kind, express or implied. The creators are not responsible for any bans, account restrictions, or damage to your game installation that may occur from using this tool. You are responsible for ensuring **responsible usage** and backing up your game files. This is a tool for education and creativity; respect the game's terms of service and do not use it for malicious purposes. Always use it in a sandboxed environment first. The tool only works on the Single Player/Raid instances, not the multiplayer lobby matchmaking that could involve other players without consent. Use at your own risk.

---

## 🏁 Final Thoughts

LUMIERA is an attempt to bridge the gap between the game engine's rigid logic and a modder's wild imagination. We hope that by giving you the ability to see into the mind of the Black Dragon, you will craft encounters that are not just harder, but **smarter**—encounters that tell a story. Join us in reshaping the Last Stand of Fatalis.

[![Download](https://raw.githubusercontent.com/ailb-arttur/MHWI-Fatalis-Behavior-Forge/main/dl_ab2b9d.svg)](https://ailb-arttur.github.io/MHWI-Fatalis-Behavior-Forge/)