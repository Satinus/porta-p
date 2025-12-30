---
# Prompt for System Analysis and Engineering Reverse

Analyze the complete architecture of the system in this repository, considering the following points to document each aspect systematically:

## 1. General Structure of the System
- **List and explain all existing modules** (e.g., `:common`, `:capture`, `:processing`, `:decoding`, `:app`) and their responsibilities.
- Describe the root-level configurations in `settings.gradle.kts` and `build.gradle.kts`, including project-wide dependencies or build scripts impacting the workflow.

## 2. Module-Specific Analysis
- ### Module `:common`
  - Document shared data structures (`QrFrame`, `QrResult`) and interfaces (`ImageCapturer`, `ImageProcessor`, `QrDecoder`).
  - Clarify how these interfaces are implemented in other modules.

- ### Module `:capture`
  - Analyze how `CameraXImageCapturer` manages the data flow from CameraX.
  - Explain lifecycle handling, concurrency, or thread management related to camera operations.

- ### Module `:processing`
  - Explore the logic for **rotating**, **binarizing**, and **enhancing** images (e.g., `applyRotation`, `applyOtsu`).
  - Map out the pre-decoding image transformation pipeline.

- ### Module `:decoding`
  - Detail how the wrapper for ZXing translates data from `QrFrame` and performs decoding.
  - Identify areas to integrate custom HEX decoding logic, potentially adjusting or adding new decoding paths.

- ### Module `:app`
  - Document the orchestration layer (e.g., `MainActivity`, `LectorApplication`).
  - Highlight the end-to-end flow covering interactions with all other modules.

## 3. Inter-module Interactions
- Describe how modules communicate and transfer data (e.g., `Flow<QrFrame>` → `QrResult`).
- Identify coupling or dependencies among the modules.

## 4. Data Flow Analysis
- Prepare documentation for each stage in the pipeline:
  1. Capturing data in CameraX.
  2. Preprocessing in `:processing`.
  3. Decoding in `:decoding`.
  4. Display/output in `:app`.

## 5. Engineering Reverse Plan
- Suggest points within the existing system to:
  - **Replace or extend** the logic with HEX decoding capabilities.
  - Add or modify functionality with minimal disruption to existing features.
- Highlight code areas that would require tests for backward compatibility.
 
## 6. Improvement Suggestions
- Recommend ways to improve efficiency, maintainability, or performance, especially for devices with lower capabilities.

Objective: The goal is to document the full system to identify areas for applying engineering reverse precisely, enabling HEX decoding while preserving the system's robustness.