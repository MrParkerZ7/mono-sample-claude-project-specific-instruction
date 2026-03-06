# Format Architect - Spacing Style Guide

## Overview

This document defines **minimum spacing rules** for infrastructure architecture diagrams. Objects can have more space between them as needed for visual clarity.

## Grid System

- Grid size: `10px` (1 block)
- All spacing values are **minimums**

## Minimum Spacing Rules

### Containers

| Rule | Minimum Value | Description |
|------|---------------|-------------|
| Margin from parent | `10px` (1 block) | Minimum distance from parent container edge |
| Title padding | `+20px` (2 blocks) | Additional top space for containers with titles |
| Content start Y | `30px` minimum | For titled containers: 10px margin + 20px title |

### Shapes/Icons

| Rule | Minimum Value | Description |
|------|---------------|-------------|
| Margin from edges | `10px` (1 block) | Minimum distance from container edge |
| Bottom label space | `+20px` (2 blocks) | Additional space for shapes with bottom text labels |
| Horizontal gap | `30px` minimum | Minimum space between adjacent icons (edge-to-edge) |

### Icon Size Standard

**Rule: The shorter side must be at least 4 blocks (40px)**

| Aspect Ratio | Size (blocks) | Size (px) | Example |
|--------------|---------------|-----------|---------|
| 1:1 (square) | 4 x 4 | 40 x 40 | Standard service icons |
| 1:2 | 4 x 8 | 40 x 80 | Tall icons (e.g., person, server rack) |
| 2:1 | 8 x 4 | 80 x 40 | Wide icons (e.g., load balancer banner) |
| 2:3 | 4 x 6 | 40 x 60 | Slightly tall icons |

**Calculation:** `shorter_side = 4 blocks (40px)`, then scale the longer side proportionally.

### Container Height Guidelines

| Content | Minimum Height | Calculation |
|---------|----------------|-------------|
| Single row (4x4 icons) | `100px` | 30 (title) + 40 (icon) + 20 (label) + 10 (margin) |
| Two rows (4x4 icons) | `170px` | 30 + (40+20)×2 + 10 gap + 10 margin |

## Key Principles

1. **These are minimums** - Use more space when it improves readability
2. **Visual balance** - Adjust spacing for visual harmony, not strict grid alignment
3. **Content-driven** - Let the content determine actual spacing needs
4. **Consistency within groups** - Similar elements should have consistent spacing
