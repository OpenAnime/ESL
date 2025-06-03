# ESL: Expressive Subtitle Language

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**ESL** is an open-source initiative defining a rich, human-readable subtitle format designed for expressive and dynamic text presentations. It leverages the clarity of HCL (HashiCorp Configuration Language) to provide a comprehensive framework for timed text, intricate styling, complex motion effects, and karaoke.

## Key Features

*   **Expressive Styling:** Hierarchical styles, per-cue overrides, fine-grained control over fonts, colors, borders, shadows, and alignment.
*   **Advanced Motions:** Define reusable, multi-property animations (opacity, position, scale, rotation, shear) with various easing functions and precise timing.
*   **Karaoke Support:** Built-in syntax for word-by-word or syllable-by-syllable text reveal.
*   **Human-Readable Syntax:** Based on HCL, making files easy to write, read, debug, and version control.
*   **Structured & Modular:** Logical organization into `meta`, `style`, `motion`, and `cue` blocks promotes maintainability.
*   **Extensible:** Designed with future enhancements in mind.

## Specification

The definitive guide to the ESL format, its syntax, and semantics can be found in the official specification:

➡️ **[Read the ESL Specification (Version 1.0)](https://github.com/OpenAnime/ESL/wiki)**

This document details all available blocks, attributes, data types, and conventions for creating valid ESL files.

## Examples

**A simple ESL file (`example.esl`):**
```hcl
meta {
  title       = "Simple Demo"
  esl_version = "0.1.0"
  resolution  = [1920, 1080]
  default_style = "default"
}

style "default" {
  font_family = "Arial"
  font_size   = 48
  color       = "#FFFFFF"
  align       = "bottom-center"
  shadow      = [2, 2, 3, "#00000080"]
}

motion "fade_in_quick" {
  duration = 300
  opacity  = [0, 1]
}

cue {
  in    = 1000
  out   = 5000
  text  = "Hello, World!"
  style = "default"
  motion_in = ["fade_in_quick"]
}
```
