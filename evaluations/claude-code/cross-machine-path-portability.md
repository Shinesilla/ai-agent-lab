# Cross-Machine Path Portability

**Problem:** A script or automation hook developed and tested on one machine worked correctly there, but failed — sometimes silently — when the same code ran on a second machine, because it embedded an absolute file path specific to the first machine's filesystem layout.

**Approach:** The failure class was root-caused first: any script that hardcodes a machine-specific path, instead of deriving it at runtime, will break the moment it runs somewhere else — the bug is invisible on the machine where it was written and only surfaces on the second one. A portability check was built to run at authoring time, scanning for hardcoded absolute paths and failing the build immediately, rather than letting the bug ship and surface later as a confusing runtime failure on a different machine.

**Result:** The failure class moved from "discovered at runtime, sometimes silently, on whichever machine hits it first" to "caught at authoring time, on the machine where the code was written." The fix generalizes beyond the original bug — it functions as a standing regression gate that stays useful for any future script or hook added to the same codebase.
