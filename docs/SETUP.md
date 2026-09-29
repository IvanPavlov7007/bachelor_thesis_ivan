# Setup and project layout

This page describes the checked-in project as of 29 September 2026. The
[historical documentation](archive/Documentation-2024.pdf) described a Unity
2022.3.41d1 project. Its setup instructions are not current.

## Open the project

1. Clone the repository and open `dev/Avatar creator/` (the folder containing
   `Assets/`, `Packages/`, and `ProjectSettings/`) in Unity Hub.
2. Use Unity **6000.2.10f1**, the version recorded in
   `ProjectSettings/ProjectVersion.txt`. Allow Unity to import the project and
   resolve the packages recorded in `Packages/manifest.json` and
   `Packages/packages-lock.json`.
3. Open `Assets/Avatar creator/Scenes/Customized Options.unity`. This is the
   only enabled scene in `ProjectSettings/EditorBuildSettings.asset`.

Importing a large Unity project can take time. Compilation in this editor
version was checked after the recent migration fixes, but a clean clone,
Play mode, Android build, and headset deployment have not been verified.
See [Testing](TESTING.md).

## Where to find things

| Path | Contents |
| --- | --- |
| `Assets/Avatar creator/` | Project-specific scripts, scenes, prefabs, materials, models, textures, and customized UMA content. |
| `Assets/UMA/` | Bundled UMA framework and content used by the avatar system. |
| `Assets/Plugins/` | Imported packages and assets, including the VR template content. |
| `Packages/` | Unity Package Manager dependencies. |
| `ProjectSettings/` | Unity project and build scene settings. |

The other scenes in `Assets/Avatar creator/Scenes/` were used for testing or
capturing UI. They are not enabled in the checked-in build settings. The main
scene's current name, `Customized Options`, is historical; a clearer name
such as `AvatarCreator` can be adopted after migration testing, with Unity
references and build settings checked at the same time.

## UMA prefab dependency

The main scene references `Assets/UMA/Getting Started/UMA_GLIB.prefab` by
Unity asset GUID. Its matching `.meta` file must accompany it. Both are
explicitly included by the Unity project's `.gitignore`, although most of
UMA's `Getting Started` and `Examples` folders are ignored. The pair was
restored from a locally cached UMA 2 package to resolve the scene reference.
Do not replace the `.meta` file with a new one, since that changes its GUID.

The repository includes imported third-party content. Its reuse and
redistribution terms need separate review; the [thesis license](../LICENSE.md)
does not cover the Unity project or those assets.

## Device setup

The thesis-era prototype was used with Meta Quest 3. Current Android and
headset setup instructions have not been verified after the Unity 6 migration,
so this page does not claim a working device build. Record a verified build
procedure and device results in [Testing](TESTING.md) when hardware is
available.
