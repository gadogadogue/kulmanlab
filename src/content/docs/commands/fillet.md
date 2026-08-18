---
title: Fillet Command — Round a Corner With a Tangent Arc
description: The Fillet command rounds a corner between two Line, Arc, or Polyline segments with a tangent arc of a specified radius. Filleting a polyline's own corner folds the arc in place; filleting across an open polyline merges both sides into one new polyline.
keywords: [CAD fillet command, round corner CAD, fillet arc, tangent arc, polyline fillet, arc fillet, kulmanlab]
group: edit
order: 11
---

# Fillet

The `fillet` command rounds a corner between two [Line](../line/), [Arc](../arc/), or [Polyline](../polyline/) segments by inserting a tangent arc of a given radius, trimming (or merging) the picked entities back to where the arc begins.

Fillet works on **Line, Arc, and Polyline** entities — including a polyline's own straight or arc segments.

## Using fillet

1. Type `fillet` in the terminal or click the **Fillet** toolbar button.
2. **Type the fillet radius** and press **Enter**.
3. **Click the first line, arc, or polyline segment** — the portion you click determines which side of any intersection is kept.
4. **Hover over the second entity** — a dashed arc preview shows the resulting fillet. Move the cursor to the side you want to keep.
5. **Click** to apply.

```
  Before:                     After fillet (radius r):

  ──────────────              ──────────╮
                │                        ╰────
                │
```

## Side selection for intersecting entities

When two entities cross each other, the fillet is applied on the corner defined by the click positions — the portion of each entity on the **same side as the cursor** is kept.

- Click near one end of the first entity to select that half.
- Move the cursor to the desired half of the second entity — the dashed preview updates live.

## What the command creates

What comes out depends on what you picked:

- **Two standalone Lines/Arcs**, or any pair that doesn't involve an open polyline: both trimmed back to the tangent points **T1**/**T2**, and a new Arc entity is inserted between them.
- **Two segments of the same polyline sharing a corner vertex**: no new entity — the fillet becomes part of the polyline itself. The corner vertex is replaced by the two tangent points, and the arc between them is stored as that edge's bulge, exactly how a rounded polyline corner round-trips through DXF.
- **Anything else involving an open polyline** — two different open polylines, or an open polyline and a standalone Line/Arc: the two are merged into a **single new polyline**, each side kept up to its tangent point and joined by the fillet arc as one more bulge segment, replacing the original entities.

The inserted or extended arc inherits the current lineweight, color, layer, and linetype settings (or the polyline's own, when it folds into one).

## Corners with no real angle to round

If the two picked segments already meet tangentially at a shared vertex — a straight polyline corner, or a line running smoothly into a tangent-continuation arc segment — there's no real corner for any circle to round. Fillet detects this and refuses with `cannot fillet: no tangent circle fits there` instead of drawing a stray loop.

## Keyboard reference

| Key | Action |
|-----|--------|
| `0`–`9`, `.` | Append digit to the radius value |
| `Backspace` | Delete last typed character |
| `Enter` / `Space` | Confirm the typed radius and move to entity selection |
| `Escape` | Cancel and reset |

## Supported entities

| Entity | Supported |
|--------|-----------|
| Line | Yes |
| Arc | Yes |
| Polyline (straight or arc segment) | Yes |
| Circle, Ellipse | No |
| Text, Spline, Dimension, Leader | No |

## Fillet vs Chamfer

| | Fillet | Chamfer |
|---|--------|---------|
| Corner type | Rounded arc | Straight cut |
| Input | One radius | Two distances (d1, d2) |
| Inserted entity | Arc | Line |
| Supported entities | Lines, Arcs, and Polylines (straight or arc segments) | Lines and Polylines (straight segments only) |
