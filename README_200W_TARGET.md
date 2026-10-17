# 200 W mono / 4 ohm Class-D amplifier target

This KiCad project uses the **TPA3255** rather than the TPA3116D2.  The TPA3116D2 cannot provide 200 W.

## Intended operating point

| Item | Target |
| --- | --- |
| Topology | TPA3255 PBTL (mono) |
| Loudspeaker load | 4 ohm nominal |
| Supply | 48 V DC, minimum 8 A, isolated SELV supply |
| Output target | 200 W RMS continuous |
| Speaker voltage limit | 28.3 V RMS maximum (40 V peak) |
| Speaker current | 7.1 A RMS / 10 A peak |

Set the input level or upstream gain so a sine-wave test produces no more than 28.3 V RMS at the speaker terminals.  The board is capable of more power at 48 V, so this limit is essential for the 200 W target.

## Before building

1. Use a current-limited bench supply for initial power-up, then a 48 V / 8 A or higher supply for load testing.
2. Fit output inductors and polypropylene filter capacitors with adequate ripple-current and voltage ratings.
3. Use a heatsink plus forced airflow; check inductor and heatsink temperature at full load.
4. Perform ERC/DRC and a qualified design review before sending the board for manufacture. This is a high-energy power-amplifier reference, not a certified product.

## Files

Open `TPA3255PBTL.kicad_pro` in KiCad. `board_preview.png` is a rendered board check.

The design derives from the MIT-licensed `TPA3255_ClassD_PBTL` reference by Eli Mattingly. The required MIT license is included as `LICENSE`. Design choices should be verified against the [TI TPA3255 datasheet](https://www.ti.com/lit/ds/symlink/tpa3255.pdf) and [TPA3255EVM documentation](https://www.ti.com/tool/TPA3255EVM).
