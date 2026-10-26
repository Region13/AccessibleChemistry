# Chemistry Workbench

A single-page web app that lets a student write chemistry work without typing or dragging. It was built for a high school general education chemistry student who uses eye gaze (iPad with iOS Eye Tracking or AssistiveTouch). Every function is a large tap or dwell target. Finished work collects into one document that copies into Google Docs, Word or Pages.

The app is one file (`index.html`). It has no server, no account, no build step and no analytics.

## Status

Proof of concept, version 1. It has been checked with scripted browser tests at tablet sizes and with an automated accessibility scan (axe-core). It has **not** been tested with a screen reader, with eye tracking hardware, with the student, or by pasting into Google Docs, Word or Pages on an iPad. See "Needs review before classroom use" below.

## What it does

| Tab | Purpose |
| --- | --- |
| Formula | Build formulas from elements and 40 polyatomic ions with subscripts, charges and brackets, such as Ca(OH)₂ and [SO₃]²⁻. |
| Structure | Draw bonded structures on a grid: single, double and triple bonds, lone pairs, atom charges, and brackets with an overall charge. |
| Name | Build compound names from prefixes (mono- to deca-), Roman numerals, acid parts (hydro-, -ic, -ous), element names and ion names. |
| Math | Write calculations, including stacked fractions for unit conversions, scientific notation, exponents, units and symbols. |
| Calculator | Optional (off by default). Arithmetic, powers, roots, log, ln, significant figure rounding. Results insert into the document or the Math tab. |
| Atoms | Isotope and nuclear notation with stacked mass and atomic numbers, electron configurations, and Lewis dot symbols. |
| Data | Build a data table with a header row, units and headings. It pastes as an editable table. |
| Words | Word bank, symbols, numbers, and a text box for typing with the device keyboard or dictation. |
| Table | Full periodic table on one screen, or large buttons one family at a time. Shows electronegativity, valence electrons and typical charges. |
| Document | The running document. Select and delete items, copy everything, or read it aloud. |

A document strip stays at the top of every tab. Choosing "Insert into document" on any tab adds the work there.

## Accessibility features

- Tap to place everywhere. Nothing needs dragging, holding or double tapping.
- Targets are at least 40 px and mostly 50 px or larger, with space between them. Long lists are paged with Previous and Next buttons so the screen does not scroll on a tablet in landscape.
- Settings (full screen): text size, Andika or Atkinson Hyperlegible font, Auto, Light, Dark and High contrast themes, increased text spacing, a 24 px minimum text mode, voice output with a Stop button, dwell click with adjustable time, and an optional calculator.
- Optional passcode on teacher controls (calculator) or on all settings. It is a classroom deterrent only and is stored in the browser.
- Selected buttons use a bar and fill, not color alone. Toggles use `aria-pressed`. Messages and results go to a live region.
- Keyboard operable, with visible focus. The structure grid can be used by keyboard.
- No time limits, no flashing, no automatic audio. Dwell click is off by default because iOS Eye Tracking and AssistiveTouch already provide it.
- Pasted subscripts, superscripts and charges stay as text. Structures, Lewis symbols, nuclear notation and fraction calculations paste as pictures with alt text. Tables paste as tables.

Known gaps:

- Scanning access (board or auditory) is not included.
- No Spanish interface.
- Voice output uses the device voice and reads subscripts as "sub".
- The default layout fits one screen, so some labels are smaller than 24 px. The "24 px minimum" setting meets that floor but screens may scroll.

## Curriculum alignment

Aligned to the Texas Chemistry TEKS, 19 TAC §112.43, checked against the Cornell LII copy and not the official TEA text:

- Formula, Name: (7)(B), (12)(A)
- Structure: (6)(E), (7)(C)
- Table: (5)(B), (5)(C), (7)(A)
- Math, Calculator: (8), (9)(C), (11)(E), (11)(F), (12)(E), (13)(D)
- Atoms: (6)(B), (6)(E), (14)(A)
- Data: (1)(F)
- Words: (3)(B), (9)(A)

Not covered: graphs, orbital diagrams, 3D molecular shapes, balancing help, and mole or gas law solvers.

## Content to verify with the teacher

The following were written from general chemistry knowledge and are not copied from the class sheets:

- The polyatomic ion list and ion names.
- Electronegativity values (Pauling) and typical ion charges.
- Naming conventions, such as "Iron (II)" and the dropped vowel in "octoxide" and "monoxide". The Unit 7 key spells "tetraoxide" but "octoxide".
- The isotope tool fills the atomic number from the periodic table by default. This can be turned off.

## Needs review before classroom use

- Screen reader testing.
- Eye tracking and AssistiveTouch testing on the student's own iPad, including target size, spacing and dwell time. This is best done with the district assistive technology specialist or OT.
- Paste testing into the student's actual document app on iOS.
- A check of the voice output.
- A trial with the student and teacher.
- The scripted checks so far are not a formal WCAG 2.2 AA audit.

## Privacy

- No data is sent anywhere. There is no server and no analytics.
- The document, settings and passcode are stored in the browser's local storage on that device. Clearing site data removes them.
- The page loads two fonts (Andika and Atkinson Hyperlegible) from Google Fonts. To avoid this, download the fonts, host them in the repository, and replace the `<link>` tag near the top of `index.html` with `@font-face` rules. The app falls back to system fonts if the fonts do not load.

## Put it online with GitHub Pages

1. Create a new repository on GitHub.
2. Upload `index.html`, `.nojekyll`, and this `README.md` (drag the files onto the repository page and choose Commit).
3. Open Settings, then Pages. Under Build and deployment, choose Deploy from a branch, pick `main` and `/ (root)`, and save.
4. After a minute or two the site is at `https://<your-username>.github.io/<repository-name>/`.

To try it locally, open `index.html` in a browser. Copying to the clipboard may be restricted when the file is opened from disk.

## Share it to the student's iPad (Pilot)

These steps assume an iPad that the student controls with her eye gaze setup, such as a Tobii Dynavox Pilot with iPadOS Eye Tracking, AssistiveTouch or Dwell Control. The Pilot and the iPad's own accessibility settings do the pointing and clicking. The web app only supplies large, spaced targets. Whoever sets this up should be able to use the iPad directly, because the first steps need normal touch.

**1. Send the link to the iPad**

- Message, email or AirDrop the GitHub Pages address (`https://<your-username>.github.io/<repository-name>/`) to the iPad, or open it from a bookmark.
- Alternatively, print or show a QR code of the address and scan it with the iPad camera.
- If the iPad is managed by the district, ask IT to push the address as a Web Clip (a home screen shortcut) through your device management system, so nothing has to be set up on the device by hand.

**2. Open it in Safari**

- Use Safari. The Add to Home Screen steps below are for Safari, and other browsers have not been considered.
- The first load needs an internet connection. The app does not work offline.

**3. Add it to the Home Screen**

1. In Safari, tap Share (the square with an arrow).
2. Tap Add to Home Screen, then Add.
3. Open the new icon from the Home Screen. It opens full screen with no browser bars, which gives the app the most room.

The Home Screen icon keeps its own settings and its own saved document, separate from Safari. Set the text size, theme, voice and any passcode again the first time it is opened from the Home Screen.

**4. Set the iPad up for the app**

- Turn on Orientation Lock in landscape. The layout is tuned for landscape at about 1180 × 820 and fits on one screen without scrolling.
- Leave "Dwell click" off in the app's Settings. The iPad's own Eye Tracking, Dwell Control or AssistiveTouch already click. If both are on, buttons can be pressed twice.
- Set the dwell time on the iPad or Pilot first, then adjust the app's text size and theme in Settings with the student present.
- Pick the theme, font and text size that she reads most easily. Use "24 px minimum" only if she needs the larger text and can tolerate some scrolling.
- Optional: set a passcode in Settings, under Teacher controls, to keep the calculator off during tests.

**5. Pasting into her document app**

1. In the app, choose "Copy all". It shows "Copied" when it works.
2. Switch to Google Docs, Pages or Word, put the cursor where the work should go, and paste with the Pilot or AssistiveTouch menu (long press and choose Paste, or use the Paste button on the keyboard shortcuts bar).
3. Check that subscripts, superscripts and tables came through. Pictures (structures, Lewis symbols, nuclear notation and fraction calculations) paste as images.
4. If Copy is blocked, the app shows a box with the text. Select it and copy it by hand.

Testing paste on the iPad with her real document app is the most important check before classroom use.

**6. Optional: lock the iPad to the app for tests**

- Settings, Accessibility, Guided Access. Turn it on, set a passcode, then triple-click the side or Home button inside the app to start a session.
- Guided Access keeps the student in the app. Pair it with the app's passcode so the calculator stays off.

**7. Updating the app**

- When `index.html` changes in the repository, GitHub Pages updates within a few minutes. Close and reopen the Home Screen icon to pick up the new version.
- Saved documents stay on the device unless the browser's site data is cleared.

**If something does not work**

- Buttons press twice: turn the app's Dwell click off.
- Nothing pastes: copy again with "Copy all", then check Settings, Paste from Other Apps on the iPad.
- Text looks wrong or fonts are missing: the device may be offline. Reload with a connection.
- The layout scrolls: lock the iPad to landscape, and use "Fit one screen" with Normal text size.

## Files

- `index.html` is the whole app: markup, styles and script.
- `.nojekyll` tells GitHub Pages to serve the file as is.

## License

No license is set. Add one before sharing the repository outside your district.
