# State: Desired State (Quick mode)

Read this first in a new session, after loading the cinecode skill, then `py -3 C:\Users\user\.claude\skills\cinecode/scripts/init_film.py . --update-tools`. Kit: C:\Users\user\.claude\skills\cinecode · Method: `references/quick-mode.md`

- **Phase:** delivered
- **Format source:** none
- **Purpose:** ad & product (explainer, no brand) (user)
- **Idea:** How Kubernetes deploys an app and heals itself: kubectl apply, control plane schedules 3 pods on 3 nodes, a Service routes traffic, node 2 dies, the controller notices desired != actual and reschedules, 3/3 again, title "Desired state. Always." (user)
- **Medium:** motion design, dark technical blueprint / HUD (user)
- **Curiosity:** 0–2 s: what will this command set in motion? · 14 s: a node dies, will the app survive? · paid 24 s: 3/3 ready again without a human.
- **Format:** 30 s, 16:9, 1920x1080, 24 fps · **Loop:** no · **Delivered to:** project root as k8s-self-healing.mp4
- **Look · mood:** authored HUD blueprint (Canvas 2D in VIEW perspective) · exact, calm, confident
- **Director card:** see the card below · **Finishing:** none
- **Type:** own: IBM Plex Mono 400/600/700 for every role (user: monospace)
- **Sound (Q4):** on-screen text + music, no voice (user)
- **Music:** code (user) — synthesized ambient
- **Sound identity:** a dark machine-room drone; every state change of the cluster is a dry tick or click; the failure is the one low dissonant pulse.
- **References (Q5):** skip (motion design, user brief complete)
- **Beats:** see card
- **Key moments:** 3.5 s Enter · 9.5 s 3/3 ready · 15 s node-2 NotReady · 24 s 3/3 ready again · 27 s title
- **Thesis line:** Desired state. Always. (user)
- **Low key by choice:** the dark HUD board is the user's brief (TOO DARK named, kept); bright stretches: green flash at 24 s and the green title band 27–30 s.
- **Last output:** renders/film-v2.mp4 (final 1920x1080, -14.0 LUFS) copied to k8s-self-healing.mp4 here and in Documents; viewer critique-v7: no red items
- **Open notes:** none
- **Revision round:** 0 of 2
- **Next action:** card shown, waiting for OK; then stills at 10 s and 17 s

## Card

BPM 120 (bar = 2 s): cues 4 / 12 / 14 / 20 on bar lines, 27 on a beat.

| t | beat | what changes | camera | in | sound |
|---|---|---|---|---|---|
| 0–4 | hook | cursor blinks on frame 0, `kubectl apply -f deployment.yaml` types itself, Enter at 3.5 | slow push in 4 % | — | key ticks, Enter click |
| 4–12 | build | terminal folds into a corner; control plane lights: api-server 4.2, etcd 4.7, scheduler 5.2, links draw; spec card `replicas: 3`; scheduler fires 3 pods on arcs to node-1/2/3 at 6.5 / 8.0 / 9.5, each lands and turns green; counter 0/3 → 3/3 | tilt down from control plane to node row, perspective board | match (terminal line becomes the API link) | soft pad enters; a click per pod landing |
| 12–14 | flow | Service bar connects to the 3 pods; traffic packets run evenly | truck right 6 % | cut | packet ticks, low pulse |
| 14–20 | turn | 14.5 heartbeats stop on node-2; 15.0 node-2 red `NotReady`, its pod goes hollow; counter `2/3 ready` red; packets reroute to 2 pods | 0.4 s jolt, then slow push to node-2 | cut | missed-heartbeat ticks, one low dissonant hit, pad drops to drone |
| 20–27 | heal | controller loop: `desired 3 ≠ actual 2`; scheduler sends pod to node-3 (20.8), amber Pending → green Running at 24; counter 3/3 green; traffic re-evens | pull back to full cluster | cut | riser 22–24, resolve chord at 24, clicks |
| 27–30 | end | grid fades, title `Desired state. Always.` types on, cursor holds | locked | dissolve 0.5 | last chord, a single tick on the final period |

- **Code fit:** cluster as a drafted HUD diagram on a dark board seen in shallow perspective (VIEW, 18° tilt): nodes are rack outlines with ID plates, pods are rounded hex tiles, control plane is three labelled modules. Nothing realistic, nothing cheap: every surface carries the grid, hairline dimension ticks and IDs.
- **Palette:** ground #080c0b · grid #15211d · line #c8d4ce · dim #51625b · ok #3ee08f · fail #ff4a3d · pending #f0b24a (only for Pending, once).
- **Atmosphere:** one place, the board: light from the lit elements themselves (soft glow on green and red), far edge of the board fades into haze.
- **Light arc:** neutral → green (9.5) → red spill (15) → green returns (24) → white title.
- **Motion:** pods land with a firm spring (5 % overshoot); type at 26 chars/s; camera eases in/out, never linear.
- **Signature:** the `n/3 ready` counter, top right, changes colour with the state and returns as the title's rhythm.
- **Sound:** synthetic by choice (user): pad Am9 → Fmaj7 → drone on failure → C resolve, ticks/clicks synthesized.
- **Checks:** 10 s (3 pods green on 3 nodes, labels legible at phone size) · 17 s (node-2 clearly red, 2/3 counter, traffic only on 2 pods).
