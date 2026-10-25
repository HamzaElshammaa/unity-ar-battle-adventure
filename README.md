<div align="center">

# Unity 6 Augmented Reality Multi-Stage Battle Adventure 🥽⚔️

### **Plane-Tracked AR Puzzles, Physics Creature Capture & Turn-Based AR Combat**

[![Unity 6](https://img.shields.io/badge/Unity-6000.0_LTS-000000?style=for-the-badge&logo=unity&logoColor=white)](https://unity.com/)
[![C#](https://img.shields.io/badge/C%23-.NET-239120?style=for-the-badge&logo=csharp&logoColor=white)](https://learn.microsoft.com/en-us/dotnet/csharp/)
[![AR Foundation](https://img.shields.io/badge/AR_Foundation-ARCore_%2F_ARKit-4285F4?style=for-the-badge)](#)
[![XR Interaction Toolkit](https://img.shields.io/badge/XR_Interaction_Toolkit-3.x-FF6B6B?style=for-the-badge)](#)

*A three-stage mobile Augmented Reality game built with Unity 6, AR Foundation, and XR Interaction Toolkit — guiding players from real-world surface puzzle solving to physics-based creature capture and real-time AR combat.*

</div>

---

## 🎮 Three-Stage Gameplay Architecture

```text
┌─────────────────────────────────────────────────────────────────────────┐
│ Stage 1: AR Spatial Number Puzzle (`Assets/Scripts/Puzzle/`)            │
│  • Detects real-world horizontal planes via AR Foundation raycasting    │
│  • Spawns interactive 3D number nodes (`NumberObject.cs`, `TapInput`)   │
│  • Validates sequential puzzle completion via `ARPuzzleManager.cs`      │
└────────────────────────────────────┬────────────────────────────────────┘
                                     ▼
┌─────────────────────────────────────────────────────────────────────────┐
│ Stage 2: AR Creature Collection (`Assets/Scripts/Collection/`)          │
│  • Spawns collectibles anchored in physical space (`Collectible.cs`)    │
│  • Swipe-to-throw Pokéball physics (`PokeballThrower.cs`, `Projectile`) │
│  • Tracks inventory & progression via `CollectionManager.cs`            │
└────────────────────────────────────┬────────────────────────────────────┘
                                     ▼
┌─────────────────────────────────────────────────────────────────────────┐
│ Stage 3: Interactive AR Arena Combat (`Assets/Scripts/Battle/`)         │
│  • Summons captured companion to battle an AR boss (`EnemyController`)  │
│  • Real-time health & combat state machine (`BattleManager.cs`, `UI`)   │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 📂 Project Structure

```text
├── Assets/
│   ├── Scripts/
│   │   ├── Core/               # GameManager, SceneLoader, UIStateManager, XR Simulator utilities
│   │   ├── Puzzle/             # Stage 1: ARPuzzleManager, NumberObject, TapInputHandler
│   │   ├── Collection/         # Stage 2: CollectionManager, PokeballThrower, PokeballProjectile
│   │   └── Battle/             # Stage 3: BattleManager, PlayerCombat, EnemyController, HealthSystem
│   ├── Scenes/                 # Modular Unity scenes for Puzzle, Collection, and Battle stages
│   └── XR/                     # ARCore / XR Interaction Toolkit configuration profiles
├── Packages/                   # Unity Package Manager manifest (`manifest.json`)
├── ProjectSettings/            # Unity 6 project & XR Plug-in Management settings
└── docs/                       # Project specification & AR task documentation PDFs
```

---

## 🚀 Opening & Running in Unity 6

1. Open **Unity Hub** and click **Add** → **Add project from disk**, selecting this repository root.
2. Open the project using **Unity 6 (`6000.0.x`)** with **Android Build Support (ARCore)** or **iOS Build Support (ARKit)** installed.
3. For in-editor testing without a physical phone, the project includes custom XR Device Simulator tooling (`Assets/Scripts/Core/XRSimulatorFixer.cs` and `EditorCameraController.cs`).
4. To deploy to an ARCore-compatible Android device:
   - Open **File → Build Profiles → Android**, connect your device via USB Debugging, and click **Build And Run**.
