# Client Source Repository

This repository contains the source code necessary to compile the game client executable.

## How to build

> cmake -S . -B build
>
> cmake --build build

---

## Changelog 📋

### 🐛 Bug Fixes
* **Character Selection:** Corrected the display of character stats and ensured gauge bars accurately reflect the character's stats during the selection phase.
* **Changing skill group:** Fixed an issue involving incorrect skill dictionary clearing/restructuring when changing a skill group. This previously caused the client to be unable to find the correct skill slot after a skill group reset, preventing the display of newly added points on level-up and/or clearing cooldown and active state when used and applied new point (if clearing cooldowns for level-0 skills enabled).

### ⬆️ Feature Improvements
* **Messenger System:**
	* **Live Removal Updates:** The client now receives immediate live updates when a player is removed by a friend, improving synchronization.
* **Skill Cooldowns and States:** Enhanced reliability and persistence across numerous client actions:
	* **Persistence:** Cooldowns and active slot effects are now correctly maintained when changing the Character Window view, switching skill tabs, mounting/unmounting, leveling up a skill or relogging. This persistence is ensured for togglable, non-togglable, and togglable skills with cooldowns.
	* **Grade Transfer:** Cooldowns and active slot states are correctly transferred when a skill's grade is changed (e.g., to Master or Perfect).
	* **Reset Logic:** Skill cooldowns are cleared and/or active slots are disabled when a skill is reset (individually or via a skill group reset).
	* **Support Skills:** Support skill levels are correctly maintained when the active skill group is changed/reset.
	* **Horse Skills:** Implemented special handling to ensure horse skill cooldowns are cleared when their level is changed to 0 (via commands like `/setsk`).
	* **Combo Skills:** Combo skills are automatically disabled if their level is changed to 0 (via commands like `/setsk`).
* **.gitignore file:** Ignoring all files and directories ending in `_BAK` or `.BAK` (case-insensitive)
