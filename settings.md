# Batch Video Stabilizer: batch processing settings

[Overview](./) · [Warp settings](warp-stabilizer-settings.md) ·
[Workflow](workflow.md) · [Troubleshooting](troubleshooting.md)

Use these settings to control how [Batch Video Stabilizer for Adobe Premiere Pro](https://vakago-tools.com/batch-video-stabilizer/)
processes your queue. Configure the options before selecting **Start Queue**.


## Which clips should be processed?

| Setting                               | Default | What it does                                                                                                                                                                        |
| ------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Re-analyze already analyzed clips     | On      | Processes clips again even when their existing Warp Stabilizer analysis is complete. Turn it off to skip completed analysis. Clips with incomplete analysis can still be processed. |
| Add Warp Stabilizer if not present    | On      | Adds Warp Stabilizer to queued top-level clips that do not have it. Turn it off to process clips that already have the effect.                                                      |
| Recursively add nested clips to queue | Off     | Includes clips inside nested sequences when they already contain Warp Stabilizer. Available when reanalysis is enabled.                                                             |

Enable nested collection **before adding clips to the queue**. This option collects existing
stabilization work inside nests; it does not add Warp Stabilizer to every inner clip.
This is particular useful if you need to apply both speed remapping and stabiliztation to the same clip.

For unstabilized footage, keep **Add Warp Stabilizer if not present** enabled.
For a project containing completed stabilization, turn off **Re-analyze already analyzed clips**
to avoid processing that work again. See the [workflow guide](workflow.md) for both cases.

## Detailed analysis

**Detailed analysis** is on by default and requests Premiere's more thorough analysis.
It can take longer. Compare a representative clip before using it throughout a large queue.

A checked **Detailed Analysis** row in [custom Warp settings](warp-stabilizer-settings.md#apply-custom-values)
takes precedence over this general option. Turning off the general checkbox does not necessarily
disable a value already enabled on an existing effect.

## Max parallel analyses

The default is **1**, with choices from **1 to 8**.

- **1** processes the queue sequentially. Start here when investigating failures or working with demanding footage.
- **2 to 8** allows several clips to be analyzed concurrently. Increase gradually and compare responsiveness and total processing time.

The best value depends on your footage and computer. A larger number does not guarantee a
faster queue. If Premiere becomes slow or analysis fails, reduce this value and try a small batch.
The [official product page](https://vakago-tools.com/batch-video-stabilizer/) explains parallel batch analysis.

## Retry failed clips

**Retry failed clips** is on by default. **Max retry count** defaults to **5**, with choices
from **1 to 5**. This is the number of additional attempts after the initial attempt.

Retries apply to eligible failures. They do not automatically recover every error: failures
to configure Detailed Analysis, analysis that never starts and analysis that stops responding
require attention. Use the [troubleshooting guide](troubleshooting.md) to narrow down a problem.

## Save project

**Save project** is off by default. When enabled, the extension attempts to save the Premiere
project after the queue finishes. Stopping the run skips this completion action.

A finished queue can include failed clips, so check the individual results even when the project
was saved. This option saves the project; use Premiere's export workflow to create a video file.

## Language and saved preferences

The language selector includes **Automatic (Premiere Pro)**, English, German, French, Japanese,
Korean, Spanish, Simplified Chinese and Brazilian Portuguese. Preferences are stored locally
for later sessions.

Next: follow the [batch workflow](workflow.md), adjust [Warp Stabilizer settings](warp-stabilizer-settings.md),
or explore more editing tools at [Vakago Tools](https://vakago-tools.com/).
