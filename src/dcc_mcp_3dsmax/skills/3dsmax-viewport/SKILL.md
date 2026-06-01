---
name: 3dsmax-viewport
description: >-
  Domain skill - capture visual evidence from the current Autodesk 3ds Max
  viewport. Use when the user asks for a screenshot, visual proof, or a README
  image of the current scene. Not for rendering final frames.
license: MIT
compatibility: "dcc-mcp-core 0.17+, 3ds Max 2024+"
metadata:
  dcc-mcp:
    dcc: 3dsmax
    version: "1.0.0"
    layer: domain
    stage: scene
    search-hint: "3ds Max viewport screenshot capture visual proof readme image"
    tags: "3dsmax, viewport, screenshot, capture, visual"
    tools: tools.yaml
    intent: "Capture visual evidence from the 3ds Max viewport as screenshots for verification."
    search_aliases: ["viewport", "viewport"]
    recall_context:
      app_type: "3dsmax"
      domain: "viewport"
      workflow_stage: "authoring"
      task_category: "query"
    preconditions:
      - type: software
        name: "3ds Max"
        version: ">=2024"
    side_effects:
      creates: false
      modifies: false
      deletes: false
      exports: true
      imports: false
      file_output: true
      render: false
      targets: ["file:image"]
    produces: ["file:image", "viewport_screenshot"]
---

# 3ds Max Viewport Skill

Capture the active 3ds Max viewport to an image file for visual verification,
README examples, and agent feedback loops. Tool contracts live in `tools.yaml`.
