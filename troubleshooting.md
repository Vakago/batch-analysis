# Batch Video Stabilizer troubleshooting and FAQ

[Overview](../README-batch-video-stabilizer.md) · [Batch settings](settings.md) ·
[Warp settings](warp-stabilizer-settings.md) · [Workflow](workflow.md)

Start with a small queue and **Max parallel analyses** set to **1**. Change one setting at
a time so you can see what affects the result. 

## Where do I download the extension?

Use the [new UXP listing](https://exchange.adobe.com/apps/cc/dec09d85/batch-video-stabilizer)
for Premiere Pro 25.6 or later, or check the
[legacy CEP listing](https://exchange.adobe.com/apps/cc/107996/batch-analysis-for-warp-stabilizer)
for older versions. The [Vakago Tools product page](https://vakago-tools.com/batch-video-stabilizer/)
links to both. If you are unsure use the new UXP extension.

## Custom values do not affect an existing Warp effect

Enable **Use custom settings**, check the required **Apply** rows and enable
**Override settings on existing Warp effects** before reanalysis. A checked custom
Detailed Analysis value takes precedence over the general option when custom overrides apply.
See the [custom settings instructions](warp-stabilizer-settings.md#apply-custom-values).

## The panel is not visible

Confirm installation in Creative Cloud and check the listing's Premiere compatibility.
For UXP, look under **Window > UXP Plugins**. See the [installation steps](workflow.md#install-and-open-the-panel)
and [Adobe's UXP installation guide](https://developer.adobe.com/premiere-pro/uxp/plugins/distribution/install/).

## Adding selected clips leaves the queue empty

Select video clips in the active Premiere timeline, then choose **Add selected clips**.
The queue uses timeline selection. Follow the [small-batch workflow](workflow.md#prepare-a-small-batch)
to check your selection and queue before starting.

## A clip is skipped

Check the [batch settings](settings.md#which-clips-should-be-processed):

- A completed Warp Stabilizer analysis can be skipped when reanalysis is off.
- A clip without Warp Stabilizer is skipped when adding the effect is off.
- Nested collection includes inner clips that already contain Warp Stabilizer.

Choose settings that match whether you are stabilizing untreated footage or revisiting
an existing effect.

## Does Save project export a video?

It saves the Premiere project after queue completion. Use Premiere's export controls to
produce the final video. Also check clip results: a finished queue can contain failures.
See [Save project](settings.md#save-project).

## Report a problem or suggest a feature

Use this repository's **Issues** tab and check existing reports first. Include your extension
version, UXP or CEP, Premiere version, operating system, relevant settings, reproduction steps
and the exact error message. Screenshots of the queue and Effect Controls can help.

For downloads and product information, visit [Batch Video Stabilizer](https://vakago-tools.com/batch-video-stabilizer/).
Discover more video editing tools at [Vakago Tools](https://vakago-tools.com/).

## Analysis is slow or Premiere becomes less responsive

Reduce **Max parallel analyses** and test fewer clips. Compare whether **Detailed analysis**
is needed for the footage. Please note that Warp Stabilizer can use substantial memory and
processing time.

Higher concurrency is a throughput option, so compare total queue time rather than assuming
the highest value will perform best. See [parallel analysis settings](settings.md#max-parallel-analyses).

## A clip fails or analysis never starts

Read the clip's failure message. Try the same clip in a small queue with one parallel analysis,
then check whether Warp Stabilizer can analyze it directly in Premiere.

**Retry failed clips** automatically handles failures. Analysis that never starts, stuck analysis
and Detailed Analysis configuration failures require attention rather than repeated automatic
attempts. See [retry settings](settings.md#retry-failed-clips).

If custom settings are involved, check the entered values and any version mismatch warning.
Use **Refresh schema** when prompted, then test again. See [custom values](warp-stabilizer-settings.md#apply-custom-values).

## The image is cropped or looks distorted

Review Smoothness, Method and Framing using the [Warp settings guide](warp-stabilizer-settings.md#choose-settings-with-a-test-clip).
