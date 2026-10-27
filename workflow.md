# How to batch stabilize clips in Adobe Premiere Pro

[Overview](./) · [Batch settings](settings.md) ·
[Warp settings](warp-stabilizer-settings.md) · [Troubleshooting](troubleshooting.md)

Use [Batch Video Stabilizer](https://vakago-tools.com/batch-video-stabilizer/) to queue multiple
timeline clips for Warp Stabilizer analysis. This guide follows the UXP panel; the CEP version
can have different controls.

## Install and open the panel

Download the [UXP version from Adobe Exchange](https://exchange.adobe.com/apps/cc/dec09d85/batch-video-stabilizer)
for Premiere Pro 25.6 or later. Follow the listing's installation instructions, then open
**Window > UXP Plugins > Batch Video Stabilizer** in Premiere.
[Adobe's plugin installation guide](https://developer.adobe.com/premiere-pro/uxp/plugins/distribution/install/)
explains where installed UXP panels appear.

For older Premiere versions, check the compatibility information for the
[legacy CEP version](https://exchange.adobe.com/apps/cc/107996/batch-analysis-for-warp-stabilizer).
Both downloads are also linked from the [official product page](https://vakago-tools.com/batch-video-stabilizer/).

## Prepare a small batch

1. Open your project and the sequence containing the footage you want to stabilize.
2. Save the project before starting.
3. Configure the [batch settings](settings.md). For untreated footage, enable
   **Add Warp Stabilizer if not present**. Start with **Max parallel analyses** set to **1**.
4. If you want matching effect values across the batch, configure [custom Warp settings](warp-stabilizer-settings.md#apply-custom-values).
5. Select the video clips in Premiere's timeline and choose **Add selected clips** in the panel.
6. Review the queue and remove clips you do not want to process.

Choose a few representative shots for the first batch. After reviewing their stabilization,
use the same workflow for the remaining footage.

## Start and monitor analysis

Select **Start Queue**. The panel shows clip states such as waiting, preparing, analyzing,
stabilizing, succeeded, skipped or failed.

- **Pause Queue** pauses queue processing. Premiere's already running native analysis can continue.
- **Continue** resumes queue processing.
- **Stop All** stops the queue run. Review the timeline afterward; completed edits can remain.

When the run finishes, inspect the individual clip results. Reaching the end of the queue
does not mean every clip succeeded. If **Save project** is enabled, the extension attempts
to save the project at completion.

## Review the picture

Play each shot and check motion, crop and distortion. Change [Warp Stabilizer settings](warp-stabilizer-settings.md)
where necessary. Once the small batch looks right, try increasing parallel analyses gradually
for the next batch.

## Reanalyze existing stabilization

Enable **Re-analyze already analyzed clips** before running a batch that needs fresh analysis.
To apply custom values to existing effects, also enable **Override settings on existing Warp effects**.

For stabilization inside nested sequences, enable **Recursively add nested clips to queue**
before adding your timeline selection. Only inner clips that already contain Warp Stabilizer
are collected for reanalysis. See [clip selection settings](settings.md#which-clips-should-be-processed).

Need help with a failed or skipped clip? Follow [troubleshooting](troubleshooting.md).
For downloads and product details, visit [Vakago Tools](https://vakago-tools.com/batch-video-stabilizer/).
