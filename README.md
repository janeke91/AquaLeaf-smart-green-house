# AquaLeaf

**AquaLeaf** helps home greenhouse-and-pool owners automate climate, watering and pool safety - all in one mobile app.

## The problem

Our target user is a family or hobby grower with a small greenhouse that has a pool built into it. Today they:
- check pool pH and chlorine manually - easy to forget or get wrong
- deal with pool evaporation raising greenhouse humidity, which can damage plants
- find out about leaks, pump failures or temperature drops too late, after damage is done

## Our extra feature

AquaLeaf monitors and auto-corrects pool water quality and humidity balance, on top of the standard greenhouse automation - because our user's pool is part of the greenhouse, not a separate system. This includes pool pH/chlorine dosing, a pool heater, and energy/water savings tracking.

**Direction (track):** Resource savings - the app tracks water used by irrigation and the pool, and energy used by heating, showing the user how much was saved by automation.

## Core features (required)

| # | Module | How it works |
|---|--------|--------------|
| M1 | Authentication | Login per user; each sees only their own greenhouse |
| M2 | Dashboard | Air temperature, air humidity, soil moisture, light level - 4 live parameters |
| M3 | Remote control | Irrigation, ventilation, heating - 3 devices, on/off |
| M4 | Operating modes | Manual/auto switch; e.g. "soil moisture < 30% -> water for 2 min" |
| M5 | Notifications | Push or in-app alert when a parameter leaves its allowed range |
| M6 | History and charts | Readings stored 7+ days; chart of 2+ parameters with a selectable period |
| M7 | Settings | User sets thresholds, schedule and units |
| M8 | Failure handling | Clear "no connection" state, no crash, recovers automatically |

## Signature feature details

- Pool pH and chlorine sensor, with automatic dosing
- Pool heater as an additional controllable device
- Humidity-balance logic: vents/dehumidifiers respond to pool evaporation
- Water and energy savings report (ties to the Resource savings track)

## Architecture

Three parts, as required by the brief:
- **Greenhouse simulator** - a script that generates sensor readings and sends them to the server every 30 seconds, and accepts control commands
- **Server** - Firebase (Cloud Firestore, Authentication, Cloud Messaging); stores history, the app reads data and sends commands only through it
- **Mobile app** - Flutter, one codebase for Android and iOS

## Team

| Member | Role |
|--------|------|
| Zhansaya (janeke91) | Backend / data layer (Firebase), security, integration |
| Saida | UI/UX design (Figma, style, logo) |
| Yeren | Mobile development (screens, navigation) |
| Aziza | Testing, documentation, presentation and demo |

## Project charter

Full charter (persona, extra feature, feature list, team setup): [charter.pdf](docs/charter.pdf)

## Week 2 - Design

- **Figma prototype:** ВСТАВЬ_ССЫЛКУ
- **Architecture diagram, data structure and stack rationale:** [AquaLeaf_Week2_Architecture.pdf](docs/AquaLeaf_Week2_Architecture.pdf) ([diagram image](docs/arch.png))
- **Stack:** Flutter (Dart) + Firebase (Firestore, Authentication, Cloud Messaging)
- **Style:** black background, lime accent `#B6F23D`, fonts Inter and Space Grotesk; logo is a leaf floating in a pool

## Status

Week 2 (Design) done. Next: Week 3.
