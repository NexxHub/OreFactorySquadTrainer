ORE FACTORY SQUAD TRAINER 1.2.1
Windows x64 | Money, XP, casino, super tools, upgrades, production and time

GET STARTED
Updating from 1.2: close the old trainer and restart the game first.
1. Extract this entire ZIP to a folder.
2. Start Ore Factory Squad and load your solo save or host a session.
3. Open OFSTrainer.exe and click "Attach to game".
4. Wait for "controls ready", then select a tab and enable your options.

No mod loader is required. The app targets .NET Framework 4.8.
This trainer supports the exact GameAssembly.dll and global-metadata.dat
you supplied. Different game files require a new trainer build. All toggles
start off. Source and offline verification results are included.

FACTORY & CASINO
Money: choose an amount or use +10,000 / +100,000.
Factory XP: choose an amount or use +100 XP / +1,000 XP.
F6 adds the selected money amount while the game window is active.
F7 adds the selected XP amount while the game window is active.
The game handles level-ups, notifications and payouts through its own APIs.

Enable casino options before the next round:
- Slots: triple diamonds through the game's normal payout code.
- Roulette: force the selected winning number, 0 through 36.
  Place your bet on that number before the spin.
- Blackjack: every seated player receives an ace and a ten; dealer gets 20.
- Pachinko: bet x your selected multiplier on a valid landed bucket.
  This changes the payout, not the ball's path.
- Remove daily casino limits: temporarily waive spend and win limits.

MINING: SUPER TOOLS AND DETECTOR
Shovel, pickaxe and jackhammer have separate toggles and share three settings:
- Dig size: 1.0x to 5.0x, default 3.0x.
- Speed stat: 1.0x to 10.0x, default 5.0x.
- Damage: 1x to 20x, default 10x.
The game still applies its animation and action-delay rules; a speed-stat
multiplier is not an exact multiplier of the number of swings per second.

Extended detector range multiplies both scan distance and scan radius:
1.0x to 10.0x, default 5.0x.

Re-equip your tool or detector after enabling, changing or disabling these
options. The game caches equipped tool stats. Re-equip after resetting or
detaching too. The hooks change returned stats, leaving the level-table
assets intact. Guest clients can retain their own local cached stats.

MINING: DYNAMITE
Super Dynamite: blast multiplier 1.0x to 5.0x, default 3.0x. Throw and
detonate normally. Enlarges terrain excavation and object-breaking radius
at detonation time for everyone's dynamite in your hosted game.
Free dynamite: the host player's throws do not deduct money.
Placement limit: select 1 to 100 active sticks, default 50, for the host
player's placement check. Existing sticks are not removed when disabled.
These last two controls do not change remote clients' local placement UI.

Turning Super Dynamite off makes later detonations use normal radii.
Excavation and destroyed objects already saved are not restored.

UPGRADES & WORLD
Free upgrades: purchase equipment and factory upgrades normally. The scoped
payment is waived. Required factory levels, prerequisites and maximum tiers
still apply. The original price text can remain visible in the game's UI.
Upgrades bought while enabled remain owned when the toggle is turned off.

Faster production: effective production timing 1.0x to 20.0x, default 5.0x.
Fixed in 1.2.1: Unity's regular machine Update had its own inlined production
logic and bypassed the function hooked in 1.2. The trainer now hooks that
live path as well as the original helper and the host's progress displays.
Materials are consumed normally, and blocked outputs keep their normal
checks. A 20-second production cycle reaches its timing deadline in 4
seconds at 5x; input supply and output delivery can still limit throughput.
Remote clients' local progress displays can still use normal timing.
Turning off the toggle makes subsequent checks use the real game clock
immediately; an unfinished cycle's displayed progress can move backwards.

"Timing checks" counts boosted checks reached by running machines in this
attachment. It should increase during production with the toggle enabled.
The counter stays at its last value when disabled; it resets on reattach.
Progress-display queries do not increment it. It is not an output count.

Freeze time: uses the game's synced freeze API. Disabling, resetting or
detaching restores the freeze state captured before enabling this toggle.
If time was already frozen, it stays frozen when the toggle is turned off.
Set time: choose a 24-hour clock time and click Set time. The game's API
updates and synchronizes the time to your hosted session. Setting time is
an action; turning a toggle off does not undo that clock change.

HOST AND SAVE BEHAVIOR
Use in a solo save or a session you host. The trainer's native hooks check
host status and trainer activity. Guests use the game's original behavior.
Money, factory XP, casino winnings, factory upgrades, factory output,
excavation and time changes can affect the shared multiplayer world/save.
Back up your shared save before using these changes.

Reset all toggles disables every option. Re-equip cached tools afterwards.
Casino limits and the original clock freeze state restore on the next game
update. Detach or close the trainer to restore all installed hooks. If the
game is paused, resume it before detaching. Changes already made or saved,
such as money and purchased upgrades, are not rolled back.

IF SOMETHING DOES NOT WORK
- Waiting for game updates: resume gameplay and load your factory save.
  If you are in another scene, return to the factory/city and try again.
- Tool or detector boost seems unchanged: switch away and re-equip it.
- Production boost seems unchanged: use Trainer 1.2.1 after restarting the
  game, enable Faster production, and check that Timing checks increases.
  If it stays at zero, confirm you host the save and a machine has inputs,
  is actively producing, and has cleared its pending output.
- Clock controls unavailable: wait for the day/night controller to load.
- Guest session: host the session to enable these controls.
- Different game build: no hooks are installed when hashes differ.
- Conflicting mod/trainer: restart without the conflicting tool.
- Access denied: game and trainer must use the same privilege level.
- Queued action: keep the trainer open and resume the game. Wait for the
  acknowledgment before another action. Detach clears the queue.
- A cleanup message asks for a restart: close and restart the game.

TESTING STATUS
Compiled as a 64-bit Windows GUI application with .NET Framework 4.8
references and C# 5 compatibility. Checks cover all hook fingerprints and
whole-instruction spans against the supplied GameAssembly.dll; C# binding
and detours; native x64 calling conventions and shadow space; Windows
unwind data; normalized return addresses for six-byte comparison hooks;
exactly-once commands; casino behavior; tool result buffers; purchase and
placement guards; production timing, including the full native Unity Update,
the original 1.2 bug, idle/output-blocked branches, progress and remaining
getters, and immediate disable; synced time commands; and restoration of the
original freeze state.
Live Windows/game testing has not been possible in this environment.
Read verification/build-report.json for assertion counts and build hashes.

SOURCE
Use source\Rebuild.cmd to recompile on Windows with the installed .NET
Framework compiler. Generated native helpers are included. Python and the
listed verification dependencies are needed only to rebuild helpers or run
offline native checks. No original game binaries, assets or saves are bundled.
