# A Bulletproof Business? — Replication Package

*Anonymous repository accompanying a paper under double-blind review at
TAKEDOWN '26. All author-identifying information has been withheld; a
permanent, de-anonymized version will replace this package upon
acceptance.*

## Contents

```
code/
  keyword_classifier.py            keyword-dictionary classifier (Appendix E)
  tfidf_classifier.py              TF-IDF + logistic regression classifier (Section 3.3.1)
  llm_classifier_runner.py         prompt-based LLM classifier harness (Appendix D)
  llm_classification_prompt.txt    the exact prompt used (Appendix D.1, verbatim)
  strip_excel_metadata.py          utility: scrub hidden author metadata before uploading xlsx files
data/
  manual_checks/                   3 external validation spreadsheets (Section 3.3.2 / Appendix G)
  annotator_validation/            2 independent annotators' taxonomy-validation spreadsheets (Section 3.2.2)
```

The three classifier scripts in `code/` are documented specifications, not
finished implementations — each docstring states the exact method and
hyperparameters reported in the paper. Paste your working implementation
into each before publishing.

`data/manual_checks/` and `data/annotator_validation/` are placeholders.
Add your own spreadsheets here, ideally using these names so a reviewer
can match them straight to the paper's appendix sections:

- `data/manual_checks/labelled_domain_transfer_validation.xlsx`
- `data/manual_checks/labelled_predicted_infrastructure_validation.xlsx`
- `data/manual_checks/labelled_predicted_noninfrastructure_validation.xlsx`
- `data/annotator_validation/annotator_1_taxonomy_validation.xlsx`
- `data/annotator_validation/annotator_2_taxonomy_validation.xlsx`

(The two annotator filenames are a suggestion — adjust if your own naming
differs.)

## Before uploading the 5 spreadsheets

Run `code/strip_excel_metadata.py` on all five files first:

```bash
python code/strip_excel_metadata.py data/manual_checks/*.xlsx data/annotator_validation/*.xlsx
```

Excel embeds author / last-modified-by metadata inside the file itself —
invisible unless you go looking for it, and a common way double-blind
anonymity breaks when a working spreadsheet is uploaded as-is. Read the
script's docstring: it covers the common fields but not everything, so
also run Excel's own **File > Info > Check for Issues > Inspect Document**
on each file for full coverage.

## Environment

```bash
pip install -r requirements.txt
```

## License

Code in this repository is released under the MIT License (see `LICENSE`).
This does not extend to the spreadsheets you add under `data/`.

## Anonymous review

This repository is intended to be served through an anonymization proxy
for double-blind review (e.g. anonymous.4open.science). Before publishing
the link: remove all commit metadata, author names, and institutional
affiliations; see `CHECKLIST.md`.
