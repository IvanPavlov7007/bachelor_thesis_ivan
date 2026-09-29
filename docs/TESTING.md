# Verification status and test checklist

The project is being migrated to Unity 6000.2.10f1. A clean result in the
Unity Editor is a useful check, but it does not establish that the application
builds, launches, or works in a headset.

## What has been checked

| Area | Status on 29 September 2026 |
| --- | --- |
| Main scene compilation after script reload | Checked: `Customized Options` showed no Console errors. |
| Clean clone and import | Not checked. |
| Play mode behavior | Not checked. |
| Android build and installation | Not checked. |
| Meta Quest 3 runtime behavior | Not checked after the Unity 6 migration; no headset is currently available. |
| Other scenes | Not checked. |

The old [project notes](archive/Documentation-2024.pdf) report use on Quest 3
with Unity 2022.3.41d1. This is historical evidence, not verification of the
current project.

## Checklist for the next device session

Keep a GitHub issue open for this validation task and record the exact Unity
version, headset model, OS version, build target, and commit tested. For each
item, note pass/fail and attach a screenshot, recording, or relevant log when
it fails.

- [ ] Import a fresh clone without missing packages or scene references.
- [ ] Build for Android, install the APK, and launch it on the headset.
- [ ] Confirm head tracking and both controllers are tracked and mapped to
      the expected hands or limbs.
- [ ] Confirm the avatar's head and embodied body follow headset and
      controller movement without conspicuous offset or jitter.
- [ ] Operate buttons and sliders using controller pointer and direct poke.
- [ ] Scroll, grab, move, and resize the spatial panels.
- [ ] Switch between the available avatar bases and customize skin, body,
      posture, head, hair, and outfit.
- [ ] Check that customization appears consistently on the virtual body,
      reflection, and T-pose avatar, allowing for their intentional differences.
- [ ] Look for pose jumps or lost tracking after changing race, DNA, or wardrobe.
- [ ] Capture Console or Android logs and note any serious frame-rate or
      responsiveness problems.

If an APK seems to remain installed between attempts, the old notes describe
using `adb uninstall <package-name>`, with the package name read from Unity
Player Settings. Treat this as a troubleshooting option to verify during a
future device session, not a required installation step.

Once tested, update the status table and the root README with the actual
result. Confirmed problems should get individual bug issues with reproduction
steps and logs.
