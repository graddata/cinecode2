# Critique: draft-v7 (independent viewer)

All three v6 items are fixed. I checked each at full size:
- **api-server, 16.5-22.25 s.** The tile and its label are whole in every quarter-second crop (apistrip). The tile now
  starts a few px right of the EVENTS panel, so over "Node 2 goes down." the row reads "api-server etcd scheduler
  controller".
- **z8q, 21.75-24 s.** The pending hexagon and its orange arc now stay above "z8q / Pending", with a clear gap in every
  crop (z8q tile).
- **"Desired 3. Actual 2.", 20.5-23 s.** The caption stays full-bright through 22.5 s and dims only as the controller
  lights, at about 23 s (cap tile).

What a first-time viewer would still notice:

1. **24.75-25.25 s · the EVENTS panel clips the api-server tile again, this time during the camera move toward the
   reconcile shot.** The tile's left border disappears under the panel's right edge, and at 25.0-25.25 s the first "a"
   of "api-server" is half cut ("pi-server"). By 25.5 s the row has moved below the panel and the tile is whole again
   (api3 tile). This is the same panel and row collision as in v3 and v6, now in a third time window, and it lasts
   about 0.5 s. **Fix:** in 24.5-25.5 s, keep the control-plane row's left edge at least 12 px right of the panel, for
   example by starting the camera's downward move about 0.3 s earlier or framing the camera 15-20 px further right.
   Better still, add a check that keeps this tile clear of the panel's bounds for the whole film, not one window at a
   time.
2. **21.75 s · z8q's pending pod drops in through the "Ready" label and node-3's top border.** For about one quarter
   second the orange hexagon sits over "Ready" (first frame of the z8q tile). Because it moves, it reads as an entrance,
   but it briefly covers that text. **Fix:** start the drop about 10 px lower, or fade "Ready" under the pod for those 6
   frames.
3. **22.0 s · a short orange dash floats between the z8q pod and its "z8q" name.** It is a stray stroke, about 6 px wide
   at 540p (second frame of the z8q tile), probably the start of the orbit arc. **Fix:** start the arc at its first
   full segment, or begin it 2 frames later.

Verdict: APPROVE
Red items: none. Item 1 is a half letter that is cut for about 0.5 s while the camera moves. It does not break a frame,
but it is the fourth appearance of the same collision and is worth the small fix above before the final.
Polish: Node-3 pods still use short names ("r5t", "z8q"), while node-1 and node-2 use "web-7d4-k2x"; one naming form
would be cleaner. For 20.0-20.5 s there is no caption between "Node 2 goes down." and "Desired 3. Actual 2."; this is
fine as a breath. The 27-30 s title scene is flagged as camera-led, but the typing title and "3/3 ready" carry it. The
sound is on target: -14.0 LUFS, -1.6 dBFS peak, LRA 2.4, no silences, no scene flagged. The hook passes. There are no
pops, duplicates or repeats, and there is one hard cut, at 3.4 s. The black at 0-1.25 s is the dark terminal opening,
and the very dark look is the user's choice.
Evidence: review/qc-draft-v7/report.txt; review/qc-draft-v7/sheet-small.jpg. Full 540p frames at 13, 17, 19, 21, 23,
24.5, 26.5 and 28.5 s. Quarter-second 2x crops of the control-plane row at 16.5-22.25 s (apistrip) and 23.5-26.75 s
(api2, api3). Quarter-second 2x crops of node-3 at 21.75-24 s (z8q). Half-second caption crops at 20-24.5 s (cap). All
were made with ffmpeg in the scratchpad (v7/).
