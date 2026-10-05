# Snowflake Light Mechanism Prototype


Fan-made Elsa shoe light mechanism prototype rendered with standalone WebGL.

## Run

```sh
python3 -m http.server 4173
```

Open `http://localhost:4173/`.

## What It Shows

- Upright cylindrical sleeve touching the floor
- Six inverse-projected cutouts around the tube wall, designed from a floor-space snowflake
- A central light source leaking through only those cutouts
- A floor projection calculated from light rays passing through the cutouts
- Adjustable LED intensity, stroke width, tube height, tube diameter, light height, and target outer radius
- Oblique and overhead views, plus a physically proportioned 60-degree wall development (blue = opening)

## Projection model

The defaults retain tube height `0.91`, diameter `0.95`, and centered source height `0.77`. Values share an arbitrary scene unit, not millimetres. For wall radius `R`, source height `L`, and floor radius `rho`, the opening height is `y = L * (1 - R / rho)`. The target outer radius `2.62` therefore limits openings to about `0.6304` high.

The tube and the floor use the same aperture function. Rays from each floor point intersect the cylindrical wall before testing that aperture; wall fragments in the openings are discarded. The flat pattern uses the same snowflake segment definitions. Changing the target radius, line width, or source height redesigns the apertures immediately.

This is an ideal point-source, zero-wall-thickness geometry preview. The visible LED sphere does not model an extended emitter; brightness is illustrative. LED beam distribution, optical blur, wall thickness and shoe occlusion require physical validation. The pattern preview is not a manufacturing-ready cutting template.
