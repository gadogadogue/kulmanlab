---
title: Polyline Command — Draw Multi-Segment Paths as a Single Entity
description: The Polyline command draws any number of connected straight or arc segments stored as one LWPOLYLINE entity. Toggle Arc mode with A for AutoCAD-style tangent arc segments. Vertex and segment-midpoint grips let you reshape any part of the path, straight or curved, after creation.
keywords: [CAD polyline command, draw polyline CAD, multi-segment path CAD, polyline arc segment, LWPOLYLINE bulge, LWPOLYLINE DXF, reshape polyline, vertex grip CAD, offset polyline, kulmanlab]
group: shapes
order: 2
---

# Polyline

The `polyline` command draws a connected path of any number of straight or arc segments, all stored as a single `LWPOLYLINE` entity. Because the entire path is one object, selecting it selects every segment at once — move, rotate, or scale the whole shape in a single operation. This is the key distinction from chained [Lines](../line/), where each segment is an independent entity.

Polylines can also be **closed**: the [Rectangle](../rectangle/) command uses the same `LWPOLYLINE` entity with a close flag set.

## Drawing a polyline

1. Type `polyline` in the terminal or click the **Polyline** toolbar button.
2. **Click the first point**, or type `X,Y` and press **Enter** for an exact coordinate.
3. **Click each subsequent point** — each click adds a segment. Coordinate entry works at every step.
4. Press **Enter** or **Space** to finish (requires at least 2 points placed).

```
  ●──────●
  1st    2nd
          \
           \  segment 3 (in progress — cursor here)
            ●  ← click to add, Enter/Space to finish
```

Pressing **Escape** at any time discards all placed points and exits the command.

## Drawing an arc segment

Press **A** at any point after the first vertex to toggle Arc mode — the same inline-option pattern AutoCAD's PLINE command uses, mirroring [Rotate](../rotate/)'s `Copy` option. The prompt shows the current state as `[Arc=true]` / `[Arc=false]`, and pressing **A** again flips it back, so you can freely mix straight and arc segments in one polyline.

```
  ●──────●
  1st    2nd  ← press A: [Arc=true]
          ╲
           ╲   arc segment (in progress)
            ●  ← click to add
```

While Arc mode is on, each new segment is a **tangent-continuation arc** — AutoCAD's default arc behavior with no sub-options for center, radius, or direction. The arc starts tangent to whatever came right before it: tangent to the previous segment's own direction if that segment was a line, or tangent to the previous arc's end if it was itself an arc. The very first segment of a polyline (with no prior segment to be tangent to) defaults to heading due east.

Toggling back to `[Arc=false]` resumes straight segments from wherever the last vertex landed, and you can toggle again for another arc — there's no limit on how many times you switch within one polyline.

## Coordinate entry

Instead of clicking, type an exact position for any vertex:

1. Type the X value.
2. Press `,` — the terminal shows `[X], [Y{cursor}]`.
3. Type the Y value.
4. Press **Enter** to place the vertex.

## Angle locking and exact segment length

The same 45° snap logic as the [Line](../line/#angle-locking-and-exact-length-input) command applies between any two consecutive points. When locked to an axis:

| Key | Action |
|-----|--------|
| `0`–`9`, `.` | Append digit to the segment length |
| `-` | Negative length — reverses direction along the axis (first character only) |
| `Backspace` | Delete the last typed character |
| `Enter` | Place the next point at the typed distance |

The current accumulated length appears in the terminal prompt in real time. Clicking while locked projects onto the axis so the new vertex lands exactly on it.

## Keyboard reference

| Key | Action |
|-----|--------|
| `0`–`9`, `.`, `-` | Start X coordinate entry, or segment length when angle-locked |
| `,` | Lock X and move to Y entry |
| `A` | Toggle Arc mode for the next segment (after the first vertex, with no input in progress) |
| `Backspace` | Delete last typed character |
| `Enter` | Confirm typed coordinate or length, or finish the polyline if nothing is typed and ≥ 2 points exist |
| `Space` | Finish the polyline (same as Enter when no input is in progress) |
| `Escape` | Discard all points and exit |

## Grip editing — vertices and segment midpoints

A selected polyline shows two types of grips:

| Grip | Position | What it does |
|------|----------|--------------|
| **Vertex** | At each placed point | Drag to reposition that vertex; all connected segments stretch to follow |
| **Segment midpoint** | Centre of each segment | Drag to translate **both** endpoints of that segment together, keeping the segment length and angle intact |

The segment-midpoint grip is unique to polylines — it lets you slide an individual segment sideways without changing its length. On a [Line](../line/), the midpoint grip instead activates the Move command for the whole entity.

An **arc segment** grips the same way as a straight one — dragging either endpoint vertex or the segment-midpoint grip reshapes the arc, holding its bulge (included angle) constant and refitting it through the new position, the same refit behavior an [Arc](../arc/) entity's own grips use.

There is no single "move the whole polyline" grip. To move the entire path use the [Move](../move/) command.

## Selecting polylines

| Method | Behaviour |
|--------|-----------|
| **Click** | Selects the polyline if the click lands within hit-test distance of any segment |
| **Drag right** (strict) | All vertices must fall inside the box |
| **Drag left** (crossing) | Any segment that crosses the box boundary selects the whole polyline |

Because a polyline is one entity, a crossing selection that touches any segment selects all segments.

## Supported edit commands

Polylines support every general transformation, plus offset, trim, extend, and chamfer — arc segments are fully supported by all of these except Chamfer, which only ever picks a **straight** segment (an arc segment can't be chamfered; use [Fillet](../fillet/)-style reasoning by hand, or trim it back first):

| Command | What happens to the polyline |
|---------|------------------------------|
| [Move](../move/) | Translates all vertices by the same displacement |
| [Copy](../copy/) | Creates an identical polyline at a new position |
| [Rotate](../rotate/) | Rotates all vertices around the chosen base point |
| [Mirror](../mirror/) | Reflects all vertices across the mirror axis |
| [Scale](../scale/) | Scales all vertices uniformly from the base point |
| [Offset](../offset/) | Creates a parallel polyline at a fixed perpendicular distance — arc segments offset to a new radius, same as a standalone [Arc](../arc/) |
| [Trim](../trim/) | Removes the portion of the polyline between two intersection points, straight or arc segments alike |
| [Extend](../extend/) | Stretches the polyline's first or last segment to the next boundary — an arc terminal segment grows along its own circle |
| [Chamfer](../chamfer/) | Bevels a corner between two **adjacent straight** segments only; an arc segment at that corner is skipped when picking |
| [Delete](../delete/) | Removes the polyline from the drawing |

Fillet does not support polylines at all — pick the individual [Line](../line/) entities instead, or use an arc segment drawn directly with the Arc option above.

## Properties

When a polyline is selected the properties panel shows:

**General**

| Property | Default | Meaning |
|----------|---------|---------|
| Color | 256 (ByLayer) | ACI color index |
| Layer | `0` | Layer assignment |
| Linetype | ByLayer | Named linetype pattern |
| Linetype Scale | 1 | Scale factor on the linetype pattern |
| Thickness | 0 | Extrusion thickness |

**Geometry**

| Property | Meaning |
|----------|---------|
| Closed | Whether the last vertex connects back to the first |
| Vertex Count | Total number of vertices |
| Vertices | Coordinate list of all vertices |

## Polyline vs Line — when to use which

| | Polyline | Line |
|---|---------|------|
| Entity count | One `LWPOLYLINE` for the whole path | One `LINE` per segment |
| Closed shape | Yes (close flag) | No |
| Arc segments | Yes, per-segment via the `Arc` toggle | No — a curved segment needs a separate [Arc](../arc/) entity |
| Trim / Extend | Yes | Yes — segment by segment |
| Segment-midpoint grip | Translates the whole segment | Activates Move for the entity |
| Best for | Outlines, contours, shapes you keep whole | Construction lines, geometry you'll trim |

## DXF — LWPOLYLINE entity

Polylines are saved as `LWPOLYLINE` entities in the DXF file. All properties — vertex coordinates, closed flag, color, layer, linetype, linetype scale, and thickness — round-trip without loss. Rectangles drawn with the [Rectangle](../rectangle/) command also save as `LWPOLYLINE` (closed, four vertices) and are indistinguishable at the DXF level.

Each vertex also carries a **bulge** (DXF group code 42) — 0 for a straight segment to the next vertex, or the signed tangent-of-quarter-angle value AutoCAD itself uses for a curved one (positive bulge sweeps counter-clockwise, negative clockwise). Bulges round-trip losslessly, so a polyline with arc segments imported from another CAD application's DXF renders, selects, grip-edits, trims, extends, and hatches exactly like one drawn here with the Arc option.

`LWPOLYLINE` entities from any DXF-compatible application (LibreCAD, FreeCAD, etc.) are read back as fully editable polylines in the editor.
