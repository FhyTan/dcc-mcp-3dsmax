---
name: 3dsmax-modeling
description: >-
  Domain skill - create basic 3ds Max primitive geometry on the main thread.
  Use when adding boxes, spheres, cylinders, or planes. Not for mesh editing,
  import/export, or material assignment.
license: MIT
compatibility: "dcc-mcp-core 0.17+, 3ds Max 2024+"
metadata:
  dcc-mcp:
    dcc: 3dsmax
    version: "1.0.0"
    layer: domain
    stage: authoring
    search-hint: "3ds Max create box sphere cylinder plane primitive geometry modeling position"
    tags: "3dsmax, modeling, geometry, primitives"
    tools: tools.yaml
    intent: "Create basic 3ds Max primitive geometry: boxes, spheres, cylinders, and planes."
    search_aliases: ["modeling", "modeling"]
    recall_context:
      app_type: "3dsmax"
      domain: "modeling"
      workflow_stage: "authoring"
      task_category: "mutate"
    preconditions:
      - type: software
        name: "3ds Max"
        version: ">=2024"
    side_effects:
      creates: true
      modifies: false
      deletes: false
      exports: false
      imports: false
      file_output: false
      render: false
      targets: ["scene_node", "primitive"]
    produces: ["scene_node:primitive", "scene_node:box", "scene_node:sphere", "scene_node:cylinder", "scene_node:plane"]
---

# 3ds Max Modeling Tools

Create basic primitive geometry in the current 3ds Max scene. All tools touch
the live scene through `pymxs`, so they declare `affinity: main`.

Tool contracts live in `tools.yaml`. Scripts keep host API access behind
adapter helpers so metadata discovery remains safe outside 3ds Max.
