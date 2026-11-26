# Test Bench Safety Checklist (220V AC)

**This document must be reviewed with the academic supervisor before the first powered test.**

The bench uses a single-phase **220V AC** induction motor. Treat mains voltage as lethal. Layer 1 work does not start until the rules and hardware checklist below are understood and signed off.

## Rules

1. **Never** touch or rewire anything while the bench is powered.
2. A **second person** must be present during powered tests.
3. Keep a clear **emergency cut-off** switch within reach of the operator.
4. No loose clothing or long hair near the rotating motor.
5. Wear **eye protection** during unbalance and overload tests.

## Hardware checklist

Complete before the first powered run (and re-check after any wiring change):

- [ ] Motor and electronics mounted on a stable base
- [ ] Enclosure for all mains connections
- [ ] Properly rated fuse or RCD/GFCI on the supply
- [ ] Insulated and strain-relieved cables
- [ ] Mains wiring physically separated from the ESP32 and low-voltage side
- [ ] ACS712 wired safely with a voltage divider on its output to protect the ESP32 ADC
- [ ] DS18B20 with a 4.7k pull-up resistor
- [ ] Common ground checked
- [ ] All connections inspected before first power-up

## Fault-injection safety

| Fault type | Limits / controls |
|------------|-------------------|
| Rotor unbalance | Use a **controlled** unbalance mass only (agreed max mass and radius). Secure the mass so it cannot detach. Eye protection on. |
| Overload | Limit **duration** (agree a max seconds/minutes before each session). Watch current and temperature continuously. |
| Overheating | Set a **temperature cutoff threshold** and a **time limit**. Stop immediately if the cutoff is reached. Allow full **cool-down** before the next run. |

**How to stop a test**

1. Hit the emergency cut-off / kill switch.
2. Confirm the motor is stopping; do not approach while it spins down.
3. Wait for cool-down before touching sensors, mounts, or the motor body.

**Cool-down:** wait until measured temperature is back near ambient (or the session plan’s cool-down time has elapsed), whichever is longer.

## Emergency procedure

1. **Cut power** immediately (emergency switch / unplug at the protected supply).
2. **Do not touch** the motor until it has fully stopped.
3. **Report** the incident to the team lead and academic supervisor; note time, what happened, and any injuries or damage.

If anyone is injured, seek medical help first, then report.

## Sign-off

| Date | Tester | Reviewer | Notes |
|------|--------|----------|-------|
| | | | |
| | | | |
| | | | |

Gate 1 requires this checklist signed off — see [`docs/gates/gate-1-edge.md`](gates/gate-1-edge.md).
