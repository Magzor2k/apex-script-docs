---
layout: home
title: Home
nav_order: 1
---

# APEX Script Documentation
{: .fs-9 }

A comprehensive reference for Houdini's APEX Script language, covering syntax, patterns, and troubleshooting.
{: .fs-6 .fw-300 }

---

## What is APEX Script?

APEX Script is a Python-like language in Houdini for building APEX graphs programmatically. Unlike VEX which executes directly, APEX Script **builds graphs** that are then evaluated by the APEX runtime.

Key characteristics:
- **Graph-building language** - Creates nodes and wires, doesn't execute logic directly
- **Python-like syntax** - Familiar to Python users with type annotations
- **Meta-programming** - The script runs once to build a graph; the graph runs many times

## Quick Start

```python
# Minimal APEX Script that builds a graph
graph = ApexGraphHandle()
parms = graph.addNode('parms', '__parms__')
output = graph.addNode('output', '__output__')

# Add a TransformObject node
xform = graph.addNode('my_xform', 'TransformObject')
xform.r_in.promoteInput('rotation')
xform.xform_out.promoteOutput('transform')

# Output the graph
graph.sort(True)
geo = graph.saveToGeometry()
BindOutput(geo)
```

## Documentation Sections

| Section | Description |
|:--------|:------------|
| [Reference](reference.html) | Core syntax, types, and graph building |
| [Patterns](patterns.html) | Common patterns: FK rigs, bone deform, scene workflow |
| [Troubleshooting](troubleshooting.html) | Error messages and solutions |
| [Functions](functions.html) | Built-in function reference |
| [Types](types.html) | Type system and annotations |
| [Resources](resources.html) | External links and further reading |

## Environment

This documentation is for:
- **Houdini 21.0.559**
- **APEX Script SOP** (`apex::script`)

---

## Contributing

Found an error or want to add content? This documentation is maintained on GitHub.
