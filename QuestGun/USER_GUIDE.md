# QuestGun — Player's Guide

A virtual lightgun arcade cabinet for Meta Quest. Your Touch controller becomes
an arcade gun, and the game plays on a large screen floating in front of you.

**QuestGun is not an emulator and ships with no games.** It loads emulator cores
and game files that you supply. A fresh install cannot do anything until you add
them — see [Getting started](#2-getting-started).

---

## 1. Quick reference

| Control | Action |
|---|---|
| **Left X** *or* **Right B** | **Insert coin — press this first, before every game** |
| Right A | Start |
| Right trigger | Fire |
| Right grip | Pedal (duck / take cover) |
| Left Y | Recentre the screen on where you are looking |
| Either thumbstick click | Open / close the menu |

Credits are on both hands so you can add them without lowering the gun.

**To reload**, aim off the edge of the screen and pull the trigger, exactly as
on a real cabinet. There is no reload button.

### Starting a game — the bit everyone gets stuck on

Arcade machines take money. MAME faithfully emulates that, so a game will sit on
its attract screen ignoring you until you pay.

1. **Press Left X or Right B** to insert a coin. Press two or three times for
   extra credits if you like.
2. **Press Right A** to start.

If nothing happens when you press A, you have no credits. Press coin again.
This catches everybody at least once — the game looks like it is running,
because the attract mode is running, but it is not listening for Start.

---

## 2. Getting started

### What you need

- A Meta Quest headset with both Touch controllers
- An emulator **core** (see [Supported cores](#4-supported-cores))
- Game files you are legally entitled to use

You must supply your own game and BIOS files, from hardware you own. None are
included and none are downloaded for you.

### Where files go

Everything lives under the app's own folder, reachable over USB with no special
permissions:

```
Android/data/com.questgun.arcade/files/
├── cores/     emulator cores (*.so)
├── roms/      your games
├── system/    BIOS files, if a core needs them
└── saves/     created for you
```

Copy files there with a USB cable and your computer's file browser, or with
SideQuest's file manager.

**Multi-file disc games** — a `.gdi` or `.cue` refers to separate track files
that must sit beside it. Give each of those games its own folder inside `roms/`:

```
roms/
├── mygame.zip                      a single-file game
└── My Disc Game/                   a disc game
    ├── My Disc Game.gdi
    └── My Disc Game (Track 1).bin
```

The menu shows the `.gdi` or `.cue` and hides the track files, which are not
loadable on their own.

### Choosing what runs

Open the menu (**click either thumbstick**), pick **LOAD CORE**, then
**LOAD ROM**. That is all most people need.

To have something load automatically at startup, create a file called
`autoload.txt` in the `files/` folder:

```ini
core = mamearcade_libretro_android.so
rom = mygame.zip
```

---

## 3. Playing

The screen appears in front of you at launch. If it is off to one side, look
straight ahead and **press Left Y** to recentre it.

Point the gun at the screen. A **red laser dot** shows where you are aiming, and
your shots land there. The dot turns orange while the pedal is held.

Hold the gun like a pistol and aim down it. Do not try to line up the dot by
moving your head — the gun's barrel is the aiming line, exactly as on a real
cabinet.

### If your shots land slightly off

This is normal and adjustable. Touch controllers held like a pistol tend to
shoot a little high of where you think you are pointing.

Open the menu and adjust **GUN PITCH** (up/down) and **GUN YAW** (left/right)
until the dot sits where you are actually aiming. Small values — a degree or
two — are usually all it takes.

### The menu

Click either thumbstick to open it. It appears to your gun-hand side, clear of
the screen. Aim at it with the gun; the row under your aim highlights. **Trigger**
selects, and **either thumbstick left/right** changes values (hold to repeat).

While the menu is open the game receives no input, so nothing is fired into it
behind the panel.

| Menu item | What it does |
|---|---|
| RESUME | Close the menu |
| LOAD ROM | Browse and load a game |
| LOAD CORE | Switch emulator core, keeping the current game |
| RECENTRE SCREEN | Put the screen where you are looking |
| SCREEN DISTANCE | How far away the screen sits (1–12 m) |
| SCREEN WIDTH | How large the screen is (1–16 m) |
| SCREEN YAW TRIM | Slide the screen left or right around you |
| GUN PITCH / GUN YAW | Aim calibration |
| GUN HAND | Left or right handed |
| SHOW GUN | Draw the gun model in your hand |
| LASER SIGHT | Show the red aiming dot |
| RESET GAME | Restart the current game |
| EXIT QUESTGUN | Quit |

Settings are not saved between launches yet.

### Quick adjustments without the menu

**Hold Left grip** and the sticks retune the setup directly. Nothing reaches the
game while you hold it.

| Input | Adjusts |
|---|---|
| Right stick ↕ | Screen distance |
| Right stick ↔ | Slide the screen left / right |
| Right stick ↔ *and Left trigger* | Screen width |
| Left stick ↕ | Gun pitch |
| Left stick ↔ | Gun yaw |

### Full control list

| Right (gun) hand | |
|---|---|
| Trigger | Fire |
| Grip | Pedal — duck and take cover |
| A | Start |
| B | Insert coin |
| Thumbstick click | Menu |

| Left (off) hand | |
|---|---|
| X | Insert coin |
| Y | Recentre the screen |
| Grip (hold) | Quick adjust mode |
| Thumbstick | D-pad |
| Thumbstick click | Menu |

Swap hands with **GUN HAND** in the menu; everything above mirrors.

---

## 4. Supported cores

Cores are not bundled. Download the Android **arm64-v8a** build of the core you
want and copy it into `cores/`.

| Core | Runs | Status |
|---|---|---|
| **mamearcade** (current MAME) | Arcade | **Recommended.** Widest game list. ~250 MB |
| **mame2003-plus** | Arcade | Fast and light. Best for older games |
| mame2010 | Arcade | Middle ground |
| pcsx_rearmed | PlayStation | Installed and configured, not yet proven |
| swanstation | PlayStation | Installed and configured, not yet proven |
| Flycast | Dreamcast / NAOMI | **Does not work on Quest** — see below |

### Match your games to your core

**This is the most common cause of "the game will not load."** MAME game files
are tied to the MAME version a core was built from. A file built for current
MAME will be rejected by an older core, and the reverse is equally true.

- **mamearcade** wants current MAME files
- **mame2003-plus** wants MAME 0.78-era files
- **mame2010** wants MAME 0.139-era files

Short names can differ between MAME versions too, so the same game may be both
the wrong contents *and* the wrong file name under a different core.

If a game will not load, try the same file under a different core before
assuming the file is bad. **LOAD CORE** keeps your selected game and reloads it
under the new core, so this takes seconds.

### Flycast (Dreamcast and NAOMI) does not currently work

Dreamcast and NAOMI games load completely — BIOS, game, graphics and sound all
initialise — and then the app closes as soon as the game starts running. This is
a fault inside the Flycast core on this hardware, not something you have set up
wrongly, and it happens with every Flycast build tested.

Use MAME instead. If a Flycast game does crash the app, the next launch skips it
automatically and drops you into the menu rather than crashing again.

---

## 5. Troubleshooting

**"Core rejected content"** — the core has no driver for that game, or your game
file is for a different MAME version. Try another core via **LOAD CORE**.

**Nothing happens when I press Start** — you have no credits. Press **Left X** or
**Right B**.

**There are two aiming marks on screen** — QuestGun hides MAME's own crosshair by
writing a config file for each game the first time you load it, leaving just the
red laser dot. If you have previously changed crosshair settings inside MAME's
own menu, your file is kept and MAME's crosshair may still appear; delete
`system/mame/cfg/<game>.cfg` and reload to get the default back.

**The screen is off to one side** — look straight ahead and press **Left Y**. If
it is still slightly off, hold Left grip and nudge it with the right stick.

**My shots land near, but not on, the target** — adjust GUN PITCH and GUN YAW in
the menu.

**Shots land in the centre no matter where I aim** — the core is not receiving
the gun's position. Check you are using a supported core.

**The ROM list is empty** — files must be inside `roms/`. A disc game must be in
its own folder with its `.gdi` or `.cue` beside its track files.

**The app opened straight into the menu saying the last launch crashed** — that
is deliberate. The previous game brought the app down, so it started without
loading anything. Pick something else.

---

## 6. What this app does not do

- It contains no games, no BIOS files and no emulator cores
- It does not download anything for you
- It does not save your settings between launches yet
- It cannot make a game run faster than the headset's processor allows

Games that were designed for hardware far newer than the Quest's chip may load
and still run too slowly to enjoy. That is a limit of the hardware, not a
setting that can be changed.
