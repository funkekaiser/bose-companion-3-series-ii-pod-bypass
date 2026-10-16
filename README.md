# Bose Companion 3 Series II: control pod bypass (12-pin)

Run a Bose Companion 3 **Series II** without its control pod by bridging three pairs of pins on the 12-pin pod connector. Useful when the pod is broken, crackles, or is mechanically worn out, and a replacement pod is too expensive.

After the bypass, the system runs at fixed full volume and you control the volume from your computer. The Bass Compensation knob on the back keeps working.

> **This guide is for the square 12-pin "To Control Pod" port.** The round 9-pin version uses different pins.

There are two ways to do it:

- **[Method A: on the board](#method-a-solder-on-the-board).** Open the bass module and solder the bridges onto the back of the connector. Permanent, and nothing can slip out.
- **[Method B: from the outside](#method-b-bridge-from-the-outside).** Bridge the pins directly in the "To Control Pod" port. No opening and fully reversible, but standard jumper wires are too big for the port.

Both methods make the same three connections.

## The bridges

| Bridge  | Function                                 |
| ------- | ---------------------------------------- |
| 8 to 11 | Left channel                             |
| 9 to 10 | Right channel                            |
| 5 to 12 | Needed, exact function not confirmed     |

**Alternative to 5 to 12:** [this Reddit post](https://www.reddit.com/r/bose/comments/17eyds2/bypass_c50_on_companion_3_series_ii_subwoofer/) uses **2 to 7** instead (converted to this guide's numbering), and that also works. It's not confirmed whether 2 to 7 and 5 to 12 are the same connection. Use **one or the other, not both**: if they are different signals, bridging both would connect two circuits that were never meant to be connected.

Pins 1 and 3 are unused: the plug on the pod cable has no contacts there.

![Pod plug, pins labelled](images/06-pod-plug.jpg)

## Safety first

- **Unplug the power cord** before touching any pins. For Method A, also wait a few minutes so the power supply capacitors can discharge.
- **Set your computer volume low** before the first power-on. There is no volume control between the computer and the amp anymore.

## Method A: solder on the board

### What you need

- Phillips screwdriver
- Soldering iron and solder
- A few cm of wire (a piece of solid copper wire works well)

### 1. Open the bass module

Remove the **10 screws** on the back panel:

- **4 along the top edge of the panel.** These are hidden under the label sticker. Feel for them and cut or peel the sticker at those spots.
- **2 at the top of the heatsink**, one in each corner.
- **4 along the bottom of the heatsink.**

Then pull the whole back panel (with the heatsink) straight out a few centimetres. The amplifier board is attached to it and comes out with it, **solder side up**. Cables stay connected to the rest of the unit, so don't yank it all the way out.

![Back panel pulled out](images/02-panel-pulled-out.jpg)

![Board, solder side](images/03-board-solder-side.jpg)

### 2. Find the 12-pin connector

The connector sits right behind the "To Control Pod" port, at the edge of the board next to the panel. Since it's a right-angle connector, what you see from above are its 12 solder legs: two rows of six, running parallel to the back panel.

Number them as you see the board from above after pulling the panel out:

- **Pins 1 to 6** are the row **closest to the back panel**.
- **Pins 7 to 12** are the row further inside.
- **Pins 1 and 7** are at the end next to the screw marked with **red paint** (labelled TP327 on the board).
- **Pin 12** is next to the **TP322** label.

![Pin numbering](images/04-pin-numbering.jpg)

```
   back panel side
       |
       v
       1    7     <- next to the red-painted screw
       2    8
       3    9
       4   10
       5   11
       6   12     <- next to TP322
```

> Other guides may number the pins from the opposite side, so their top row is our bottom row. Go by the landmarks and the photo, not the numbers alone.

### 3. Solder the bridges

Solder **8 to 11**, **9 to 10** and **5 to 12** (see [The bridges](#the-bridges)).

In the photo, 8 to 11 is the larger copper loop, 9 to 10 is a solder bridge between the two neighbouring legs, and 5 to 12 is a short piece of wire.

![Bridges soldered](images/05-bridges-closeup.jpg)

Check that no solder blob touches a neighbouring leg, then slide the panel back in and put the 10 screws back.

## Method B: bridge from the outside

> This method is [reported working on Reddit](https://www.reddit.com/r/bose/comments/17eyds2/bypass_c50_on_companion_3_series_ii_subwoofer/). I didn't do it myself: standard female jumper wires (Dupont style) are **too big** to fit into the port, so I went with soldering. You'll need something thinner that makes reliable contact with the pins, e.g. thin wire or smaller crimp contacts. If you do it this way, please open an issue and share what you used.

### Pin numbering from the outside

Looking into the "To Control Pod" port from behind the unit, with the unit lying on its side as in the photo:

![Back panel with the 12-pin port, pins labelled](images/01-back-panel.jpg)

- **Pins 1 and 7** are at the end towards the **Bass Compensation knob**.
- **Pins 1 to 6** are the row **further from the heatsink**, pins 7 to 12 the row next to it.

> The pod plug photo above is the plug's face, which is the **mirror image** of the port. When working on the port, go by the back panel photo.

### Steps

1. Unplug the power cord and the pod.
2. Connect **8 to 11**, **9 to 10** and **5 to 12** in the port.
3. Make sure no bare metal touches a neighbouring pin, and secure the wires (tape or a dab of hot glue) so they can't slip out.
4. Continue with [Connect and test](#connect-and-test).

## Connect and test

1. Plug your computer into the **From Computer** input with a normal 3.5 mm stereo cable.
2. Set the computer volume low, plug in the power cord and switch the unit on.
3. **Check left and right.** On macOS: System Settings > Sound > Output, drag the balance slider fully left, then fully right. Sound should come from the matching speaker. If it's reversed, your 8/9/10/11 bridges are crossed.

## Note on other guides

This guide is based on [this video](https://www.youtube.com/watch?v=JNieR2Ab0Ck) and [this Reddit post](https://www.reddit.com/r/bose/comments/17eyds2/bypass_c50_on_companion_3_series_ii_subwoofer/). Both bridge **8 to 10 and 9 to 11** (in this guide's numbering), which swaps left and right. Use **8 to 11 and 9 to 10** instead.

## Troubleshooting

- **Nothing happens:** check that all three bridges are making contact.
- **Left and right swapped:** see [Connect and test](#connect-and-test).
- **Rattle, hum or buzz with nothing connected:** that comes from the amplifier or speakers, not the pod. This bypass won't fix it.

## Disclaimer

You do this at your own risk. The unit runs on mains power, and wrong connections can damage the amplifier.
