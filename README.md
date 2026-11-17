# Ingestion Protocol: Enterprise Data Quality Gatekeeper

An interactive game translating Enterprise Information Management (EIM) and Data Quality (DQ) concepts into *Papers, Please*-style gatekeeper gameplay.

---

## 🚀 How to Run the Prototype Right Now

The prototype is a self-contained web app with zero dependencies and built-in procedural audio.

1. Open your browser (Chrome, Edge, Firefox).
2. Open the file directly:
   `C:\Users\Monty\.gemini\antigravity\scratch\data-gatekeeper\index.html`
3. Use the mouse or hotkeys:
   - **`[A]`**: **REJECT (DROP)** - Drop corrupted, malformed, or invalid records.
   - **`[S]`**: **QUARANTINE (REVIEW)** - Route suspected duplicates, MDM conflicts, or unmasked PII.
   - **`[D]`**: **APPROVE (LOAD)** - Load validated, clean records into the Enterprise Data Warehouse.

---

## 🎮 Data Quality Concepts in Gameplay

| EIM Concept | In-Game Manifestation | Required Action |
| :--- | :--- | :--- |
| **Completeness** | Missing mandatory attributes (`NULL` customer IDs, blank emails). | **REJECT** |
| **Conformity & Validity** | Broken regex (malformed email syntax, non-existent calendar dates like Feb 31, negative order amounts). | **REJECT** |
| **Consistency & MDM** | Customer ID exists in Golden Record Cache but incoming payload has conflicting entity names or ambiguous aliases. | **QUARANTINE** |
| **Integrity & Standards** | Non-standard country entries (e.g. `GERMANY` instead of ISO 3166-1 alpha-2 `DE`). | **REJECT** |
| **Compliance & Privacy** | Raw, unmasked PII (SSNs, Credit Cards) leaked into free-text customer notes. | **QUARANTINE** |

---

## 🎨 Upgrading to 3D with Blender

When you saw the Antigravity ad mentioning **Blender**, this is how the asset pipeline connects to this exact game:

```
┌─────────────────────────────────┐      ┌───────────────────────────────┐
│     Blender (Asset Creation)    │      │         Game Engine           │
│                                 │      │  (Godot 4 or Three.js / Web)  │
│ - Retro CRT Terminal 3D mesh    │      │                               │
│ - Physical Ingestion Stampers   │ ───► │ - Loads .glb models           │
│ - Pneumatic tube delivery hatch │ .glb │ - Physics & interaction logic │
│ - Low-poly Server Racks         │      │ - Shaders & sound triggers    │
└─────────────────────────────────┘      └───────────────────────────────┘
```

### Blender Python (`bpy`) Scripting
Antigravity can write automated Python scripts that run inside Blender's scripting console to procedurally generate:
1. **The Data Terminal & Desk**: A retro-futuristic workstation with physical mechanical buttons for *Reject / Quarantine / Approve*.
2. **Data Tokens / Cartridges**: Physicalized 3D data punch-cards or magnetic cartridges that fly down a pneumatic tube onto your desk.
3. **Automated GLTF Exporter**: Scripts that auto-bake materials and export `.glb` files ready for your engine.
