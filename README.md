# Hearing Where You Are

An animated, narrated walkthrough of **acoustic geolocation** — how the Doppler
signature of an aircraft overhead, paired with public ADS-B flight data, can pin
down where a recording was made, even when the aircraft is inaudible.

**Live page:** `https://<your-username>.github.io/hearing-where-you-are/`

Nine stages, voiced start to finish: the inaudible hook, why the pitch-slide is a
fingerprint, forward-simulation (run every flight path forward instead of inverting
the sound), the hear table, reading the Doppler curve, the filter funnel
(22,801 candidate points down to 138, with silence as evidence), emission-time
physics, the locked two-curve fix, and the FDOA/TDOA parallel from RF emitter
geolocation.

## Running it

It's a static page — open `index.html`, or serve the folder:

```sh
python3 -m http.server 8000   # then visit http://localhost:8000
```

Press play (browsers block autoplay with sound, so the first click starts it).
Scrub the timeline, jump to any stage from the rail, or mute the narration.
Reduced-motion viewers get static end-states and can still play by choice.

## Files

```
index.html            self-contained page (vanilla JS canvas/SVG; Google Fonts only)
assets/narration.mp3  the voiceover track
.nojekyll             serve files as-is on GitHub Pages
```

## Scope and credits

Built for controlled technical demonstration and evaluation — not for locating
recordings made by others.

The attack, the emission-time Doppler model, and the trace-and-fit method are from
**colsto**, [*I discovered a sound that leaks your exact location (and it's
everywhere)*](https://www.youtube.com/watch?v=UytYrhYLOKI). Flight data from
[adsb.lol](https://adsb.lol). The numbers shown come from a 30×30 km synthetic
range with known ground truth.

MIT licensed.
