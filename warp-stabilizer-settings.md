# Warp Stabilizer settings for batch video stabilization

[Overview](../README-batch-video-stabilizer.md) · [Batch settings](settings.md) ·
[Workflow](workflow.md) · [Troubleshooting](troubleshooting.md)

[Batch Video Stabilizer by Vakago Tools](https://vakago-tools.com/batch-video-stabilizer/)
manages the batch queue. Premiere's Warp Stabilizer controls the appearance of each stabilized
clip. Use the UXP panel's custom settings to apply selected values across a batch.

## Apply custom values

1. Enable **Use custom settings** in the advanced settings. It is off by default.
2. Check **Apply** beside each setting you want to change, then enter its value.
3. To apply those values when reanalyzing existing Warp effects, also enable
   **Override settings on existing Warp effects**. It is off by default.
4. Test a short queue and inspect the result in Premiere's **Effect Controls** before processing more clips.

With custom settings enabled, checked values apply to newly added effects. Existing effects
receive these custom values only when the override option is also enabled. Unchecked rows
are excluded from the custom overrides.

Numeric fields require numbers. Boolean fields accept `true` or `false`. For example, to
request a Smoothness value of `20`, check its **Apply** row and enter `20`. To explicitly
disable Detailed Analysis, check that row and enter `false`. The checked Detailed Analysis
row takes precedence over the [general Detailed analysis setting](settings.md#detailed-analysis)
when the custom values apply to that effect.

Some choices appear as numeric values in the custom table. Use Premiere's Effect Controls
to inspect named choices such as **Smooth Motion** or **Subspace Warp**; avoid guessing their
numeric values. After changing Premiere versions, use **Refresh schema** to refresh the
available parameter list if the panel reports a version or settings mismatch.

## Motion and framing reference

| Control            | Meaning                                                                                                       |
| ------------------ | ------------------------------------------------------------------------------------------------------------- |
| Result             | Smooth Motion retains camera movement; No Motion attempts a locked shot.                                      |
| Smoothness         | Higher values suppress more movement and can require more cropping. Available with Smooth Motion.             |
| Method             | Position, Position/Scale/Rotation, Perspective and Subspace Warp offer progressively more complex correction. |
| Preserve Scale     | Prevents scale changes.                                                                                       |
| Framing            | Chooses visible moving edges, cropping, automatic scaling or synthesized edges.                               |
| Maximum Scale      | Limits automatic enlargement.                                                                                 |
| Action-safe Margin | Reserves a margin during automatic scaling.                                                                   |
| Additional Scale   | Adds manual enlargement after stabilization.                                                                  |

These controls are described in [Adobe's Warp Stabilizer settings reference](https://helpx.adobe.com/premiere/desktop/add-video-effects/commonly-used-effects/warp-stabilizer-settings.html).

## Analysis and advanced controls

| Control                                           | Meaning                                                            |
| ------------------------------------------------- | ------------------------------------------------------------------ |
| Detailed Analysis                                 | Uses more thorough analysis and can take longer.                   |
| Fast Analysis                                     | Speeds analysis without changing the stabilization stage.          |
| Rolling Shutter Ripple                            | Reduces rolling-shutter ripples with Perspective or Subspace Warp. |
| Crop Less <-> Smooth More                         | Adjusts the cropping and smoothing trade-off.                      |
| Synthesis Input Range                             | Sets the time range used to fill missing edges.                    |
| Synthesis Edge Feather                            | Blends synthesized edges.                                          |
| Synthesis Edge Cropping, Left, Top, Right, Bottom | Trims source edges for synthesis.                                  |
| Hide Warning Banner                               | Hides the warning display.                                         |

Edge synthesis controls apply with **Stabilize, Synthesize Edges** framing. See
[Adobe's advanced settings reference](https://helpx.adobe.com/premiere/desktop/add-video-effects/commonly-used-effects/warp-stabilizer-settings.html)
for dependencies and available controls in your Premiere version.

## Choose settings with a test clip

For an image that looks too tightly cropped, try reducing Smoothness or Crop Less <-> Smooth More.
For wobbly buildings or distorted faces, try a simpler Method such as Position, Scale, Rotation.
Use Stabilize Only to inspect how the picture moves before cropping. Adobe explains this
review process in its [video stabilization guide](https://www.adobe.com/creativecloud/video/discover/stabilize-video.html).

Compare the whole shot before applying the same values to other clips. Different camera movement
can need different settings. Follow the [workflow guide](workflow.md) to run a test batch,
or visit [Vakago Tools](https://vakago-tools.com/batch-video-stabilizer/) for product information.
