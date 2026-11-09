# Android Release Testing Checklist

A practical release QA worksheet for indie Android developers, maintained by [PlayStore12Tester](https://www.playstore12tester.com/). Copy the checklist into your release notes and record evidence for each result.

## Start with a reproducible baseline

Record the app version and build number, package name, installation source, device model, Android version, test date, and test account. Repeat failed checks on the same build before comparing devices. Use test data and sandbox purchases when available.

For every check, record **Pass**, **Fail**, **Not tested**, or **Not applicable**, plus a short evidence note. An unchecked item means the result is unknown.

## 18 checks before a release

### Installation and first use

- [ ] Install the release build on a clean device and open it from the launcher.
- [ ] Update from the previous release and confirm that existing user data is preserved.
- [ ] Complete onboarding, skip optional steps, and reopen the app to check saved state.
- [ ] Deny an optional permission, retry the related action, and check that the explanation is useful.

### Core user journeys

- [ ] Complete the main task from start to finish with realistic test data.
- [ ] Try empty fields, invalid input, unusually long text, and repeated taps on submit.
- [ ] Use Back navigation and return from another app without losing essential progress.
- [ ] Sign out and sign back in, if accounts are supported, and verify the intended access boundaries.

### Interruptions and connectivity

- [ ] Disable connectivity during a request and confirm that the app offers a recoverable error.
- [ ] Restore connectivity and retry; check that the same action is not duplicated.
- [ ] Background the app, reopen it, and check the current screen and unsaved work.
- [ ] Rotate the screen where supported and test on at least two relevant screen sizes.

### Readability, accessibility, and release details

- [ ] Increase the system text size and check that important labels and actions remain usable.
- [ ] Navigate the main journey with TalkBack and check labels, reading order, and feedback.
- [ ] Review the supported languages for clipped text, untranslated messages, and right-to-left layout where relevant.
- [ ] Test purchase, cancellation, and restore flows in a sandbox if the app sells digital access.
- [ ] Open privacy, terms, and support links from inside the app and verify the destinations.
- [ ] Review startup behavior, crashes, visible errors, and the final release notes on the exact build being shipped.

## A bug report a developer can act on

Copy this template for each issue:

```text
Title: [Screen] What failed under which condition
Build / version:
Device / Android version:
Install source:
Preconditions:

Steps to reproduce:
1.
2.
3.

Expected result:
Actual result:
Reproduction rate: __ failures / __ attempts
User impact:
Evidence: screenshot or short recording
Workaround, if any:
Retest build and result:
```

Describe observable behavior. For example, "Submit stays disabled after restoring connectivity" is more useful than "the form is broken." Attach the shortest recording that reproduces the problem, with personal details removed.

## Decide what blocks the release

- **Blocker:** The main journey cannot be completed, the app consistently crashes, or important data is lost.
- **Major:** A supported flow fails for a meaningful group of users and has no reasonable workaround.
- **Minor:** A recoverable problem or visual defect with limited impact.

Record who owns each issue and whether the fix was retested. A severity label supports a release decision; it does not replace evidence.

## Functional QA and Google Play testing requirements

This worksheet helps organize functional testing. Automated QA runs, software agents, and device sessions should not be counted as opted-in human testers. Review the current requirements and the status shown in your own Play Console separately. No checklist or testing service can guarantee production access or app approval.

Use [Google Play Console Help](https://support.google.com/googleplay/android-developer/) for official publishing guidance.

## More resources

[PlayStore12Tester](https://www.playstore12tester.com/) provides Android QA information and free browser tools for preparing test reports and release checklists. The site explains the service scope and the difference between automated QA and human testing.

Published November 9, 2026. Adapt the worksheet to your app, supported devices, and actual user journeys.
