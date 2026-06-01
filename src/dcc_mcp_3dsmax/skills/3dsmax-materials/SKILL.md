---
name: 3dsmax-materials
description: >-
  Domain skill - inspect, create, edit, and assign 3ds Max materials and
  bitmap maps on the main thread. Use when authoring Standard, Physical, or
  PBR-friendly materials, assigning node materials, and reporting texture
  connections.
license: MIT
compatibility: "dcc-mcp-core 0.17+, 3ds Max 2024+"
metadata:
  dcc-mcp:
    dcc: 3dsmax
    version: "1.0.0"
    layer: domain
    stage: authoring
    search-hint: "3ds Max material create inspect assign bitmap texture map physical pbr roughness metalness missing paths"
    tags: "3dsmax, materials, shader, assignment, bitmap, pbr"
    tools: tools.yaml
    intent: "Create, inspect, edit, and assign 3ds Max materials and bitmap textures."
    search_aliases: ["materials", "materials"]
    recall_context:
      app_type: "3dsmax"
      domain: "materials"
      workflow_stage: "authoring"
      task_category: "mutate"
    preconditions:
      - type: software
        name: "3ds Max"
        version: ">=2024"
    side_effects:
      creates: true
      modifies: true
      deletes: false
      exports: false
      imports: false
      file_output: false
      render: false
      targets: ["material", "bitmap", "scene_node"]
    produces: ["material:standard", "material:physical", "material:assignment", "bitmap_connection"]
---

# 3ds Max Material Tools

Inspect, create, edit, and assign 3ds Max materials in the current scene. All
tools touch the live scene through `pymxs`, so they declare `affinity: main`.

Tool contracts live in `tools.yaml`. `apply_material` uses current selection
when `node_names` is omitted. Renderer-specific behavior stays optional and
returns clear errors or warnings when the host does not expose that material
class or map slot.
