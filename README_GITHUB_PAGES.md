# SAJA JFDA Online Converter — GitHub Pages package

This repository is **source code only** (no approved PIL, patient data, regulatory submissions, or production identifiers are included). The webpage is a prototype and its XML output still requires full content reconciliation and live JFDA Version 4 validation.

## Publish with GitHub website (no command line)

1. Sign into GitHub at https://github.com/new and create a new repository named `saja-jfda-converter`. For a normal personal GitHub Free account choose **Public** to enable Pages. This publishes the **application source code**, not any local PDFs.
2. In the new repository choose **Add file → Upload files**. **Extract this ZIP first**, then upload all files from its root, including `index.html`, `health.html`, `.nojekyll`, and this README. Do **not** upload the ZIP itself. Commit to `main`.
3. Open the repository **Settings → Pages**. In **Build and deployment**, select **Deploy from a branch**, branch **main**, folder **/(root)**, then **Save**.
4. From Settings → Pages click **Visit site** once GitHub displays the live link. A project-site URL usually follows `https://YOUR-USERNAME.github.io/saja-jfda-converter/`. Do not guess the URL before GitHub shows it.
5. Visit the **health-check** page at `.../health.html` and confirm HTML and JavaScript pass, then visit the converter home.

**Important:** GitHub Pages is publicly reachable and is not an authenticated portal. Don't commit confidential documents to the repository. The application works client-side, but PDF.js is dynamically fetched from a third-party CDN when extracting a PDF. Have SAJA IT validate this arrangement before using confidential regulatory materials.

## Troubleshooting white screen

- Visit `.../health.html` in a private window; test `.../index.html` next.
- If `health.html` works and the app is blank, open browser Developer Tools → Console, copy the first red error, and share it.
- In Safari: Settings → Advanced → Show features for web developers; Develop → Show Web Inspector → Console.
- If the health page is blank too, check GitHub Actions → **pages build and deployment** for errors, and confirm `index.html` and `health.html` are at the repository root.
- Check that corporate network filters and browser content blockers aren't interfering.

## Converter scope

- Two- and three-column PDF extraction needs manual validation (especially Arabic).
- Six mandatory coded PIL sections use LOINC labels.
- Editable tables use XHTML with the previously tested Zithromax table arrangement.
- Exported XML is a draft until accepted by JFDA debugger; clinical content requires complete RA review.

## Sources

- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://hl7.org/fhir/R5/
- https://build.fhir.org/ig/HL7/emedicinal-product-info/en/ValueSet-sectionCode.html
