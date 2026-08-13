# Continuity and motion

## Continuity lock card

Create this card before per-shot prompts.

### Character lock

- fictional adult identity or authorized reference
- count and relationship
- height/build and hair silhouette
- outfit colors, layers, sleeves, belt, footwear, and carried objects
- starting emotional/physical state and permitted change

### Landmark lock

- silhouette, orientation, roof/floor count
- gate, ring, bridge, stair, waterfall, or tree shape
- dominant materials and motifs
- location relative to character and horizon
- features allowed to remain off-frame

### World lock

- map: start, path, destination, occluders, and travel axis
- horizon height and cardinal light direction
- cloud, river, rain, and wind direction
- time, weather, palette, neutral anchors, high-chroma accents
- material family and atmospheric density

## Per-shot motion contract

Specify eight items:

1. **Motion purpose**: reveal, follow, pressure, disorient, impact, connect, separate, or pause.
2. **Initial state**: stable opening composition.
3. **Subject action**: one readable action chain.
4. **Camera path**: one dominant movement or ordered phases.
5. **Speed curve**: still, slow, constant, accelerate, decelerate, impulse, or fast-to-settle.
6. **Extent**: approximate distance/angle and framing change.
7. **Environmental motion**: one or two supporting layers.
8. **End state**: stable last-frame composition and new information.

Example:

```text
Motion purpose: hide the destination, then reveal the travel route.
Initial state: a giant pine trunk occupies the left third; one adult traveler stands on the lower-right cliff.
Subject action: the traveler raises their gaze toward the distant gate; sleeves lift once in the wind.
Camera path: lateral dolly right for the first 3 seconds, then decelerate and hold for 1 second; no zoom or roll.
Speed curve: medium-slow constant move -> gentle deceleration -> still.
Extent: move about 2 meters, enough for the pine trunk to uncover the gate without changing character scale dramatically.
Environmental motion: cloud sea drifts left to right; pine needles move gently.
End state: the gate occupies the right third, the traveler remains 4% of frame height, and the travel path becomes visible.
```

## Movement families

- **Locked frame / static pass-by**: let action cross a stable composition; useful for tension, speed contrast, confrontation, or aftermath.
- **Push / pull / dolly**: approach emotion or retreat to reveal context; use slow, medium, fast, acceleration, or deceleration as motivated.
- **Pan / tilt / whip-pan**: redirect gaze, connect actions, reveal height, or create an impact transition. Reserve whip-pan for clear high-energy beats.
- **Lateral / diagonal parallax**: uncover architecture behind a tree, column, cliff, doorway, or foreground crowd.
- **Tracking**: trailing, leading, side-by-side, arc tracking, or long-lens follow; clarify traversal and pursuit.
- **Crane / boom / pedestal**: disclose vertical geography, stairs, waterfalls, city layers, ascent, or fall.
- **Orbit**: show relationship, encirclement, power gathering, or a decision around one stable subject. Use partial arcs when geometry is fragile.
- **Aerial / top-down / dive / rise**: establish routes, expose formations, follow sword flight, or change scale bands.
- **POV / over-shoulder passage**: make a threshold, dash, flight, or discovery subjective; keep horizon and path legible.
- **Handheld / controlled shake**: add bodily urgency at close range; keep amplitude small and duration short.
- **Optical zoom / dolly zoom**: use only for deliberate observation or perceptual shock; label as optical and avoid accidental zoom pulses.
- **Focus transition**: rack focus is a lens/focus event, not a substitute for spatial camera movement; combine only when it clarifies a gaze or reveal.

## Ordered multi-phase moves

One primary move remains the safest default. Use two or three ordered phases when the story benefits and the target model can follow them:

- `0–1s locked anticipation -> 1–4s accelerating side track -> 4–5s hard stop on the gate`
- `low trailing follow -> crane above the runner -> decelerate into top-down geography`
- `fast push through foreground mist -> pass the character -> pull focus to the approaching threat`

Write phases as a timeline. Never ask pan, zoom, orbit, roll, crane, and sprint tracking to happen simultaneously.

## Motion limits

- Match movement distance, lens, and framing change. A 20 cm move cannot turn a close-up into an extreme-wide view.
- Use one readable subject-action chain. Complex fights need multiple shots, not one overloaded prompt.
- Use one or two environmental-motion layers.
- Permit speed ramps only when tied to a beat and stated as a single curve, not random pulses.
- Use roll only for deliberate disorientation and return to a readable horizon if continuity requires it.
- Keep architecture and landmark geometry stable.
- Start and end on readable compositions unless an intentional cut-on-motion is specified.

## Cross-shot continuity

- Preserve travel direction across cuts unless a deliberate axis change is established.
- Preserve landmark screen direction or use a neutral establishing angle before reversal.
- Match wind, fabric response, cloud drift, light direction, wetness, damage, opened doors, lifted objects, and character position.
- Do not reset the character to an earlier location without a transition.
- Match outgoing and incoming motion when using action cuts; contrast motion deliberately when creating impact or stillness.

## Transitions

- cut on continued movement
- cut on gaze toward the next space
- foreground wipe by column, tree, sleeve, cloud, sword light, or eave
- match shape between moon gate, celestial ring, sun, reflection, or spell formation
- whip-pan cut for a motivated fast redirection
- sound-motivated cut when audio is part of the plan

Avoid dissolving every shot. Use dissolve for elapsed time, dream transitions, or atmospheric continuity.

## Reference-image roles

Label every image: character identity anchor, outfit anchor, landmark anchor, world/style reference, strict first frame, strict last frame, or motion reference. Do not make one image both a strict frame and a loose style reference without stating priority.
