# Repository Checklist

## Content

- [ ] `code/keyword_classifier.py` — your implementation pasted in
- [ ] `code/tfidf_classifier.py` — your implementation pasted in
- [ ] `code/llm_classifier_runner.py` — your implementation pasted in
- [x] `code/llm_classification_prompt.txt` — complete (Appendix D.1, verbatim)
- [x] `code/strip_excel_metadata.py` — complete, working utility
- [ ] `data/manual_checks/` — 3 files added
- [ ] `data/annotator_validation/` — 2 files added

## Before uploading the 5 spreadsheets

- [ ] Ran `code/strip_excel_metadata.py` on all five files
- [ ] Also ran Excel's own **File > Info > Check for Issues > Inspect
      Document** on each (catches Company/Manager fields and anything
      else the script can't reach)
- [ ] Spot-checked each file still opens correctly after stripping
- [ ] Checked inside the sheets themselves for real names — e.g. an
      "annotator" or "coder" column using real initials rather than
      "Annotator 1" / "Annotator 2", or a "notes" column with a real name
- [ ] Confirmed you're comfortable with what these 5 files disclose: the
      3 manual-check spreadsheets and 2 annotator spreadsheets likely
      contain the raw Telegram message text they were annotated against,
      which is a different (larger) disclosure than the taxonomy/keyword
      release the paper's own ethics section (3.4) explicitly assessed —
      worth a deliberate yes/no rather than a default "just upload it"

## Anonymity checklist

- [ ] No author names, affiliations, or acknowledgments anywhere: README,
      code comments/docstrings, LICENSE, commit messages, or inside the
      xlsx files themselves
- [ ] No hardcoded local file paths containing your username or student
      ID in any script
- [ ] No personal API keys / tokens in any file
- [ ] Git history is clean: create the repo fresh, or squash + orphan
      branch an existing one, so commit author name/email doesn't leak
- [ ] Served through an anonymization proxy rather than a raw
      `github.com/<username>` URL
- [ ] No links to personal websites, Google Scholar, ORCID, or lab pages
- [ ] Final pass: `grep -rni "<your name>\|<your student id>\|<your university>"`
      across every file in the repo, including the code and both READMEs

## Paper-consistency flags (still open as of the last draft reviewed)

- [ ] Ground-truth sample size inconsistent across the paper: 250
      (Section 3.2.2, confirmed correct) vs. 261 (Appendix D running
      text) vs. 262 (Table 9's caption) — reconcile all three to 250
- [ ] Three unresolved `Appendix ??` cross-references: Appendix C, the
      Appendix D LLM-model sentence, and the new Appendix G intro
- [ ] Orphaned duplicate "Table 14" caption in Appendix H.1, sitting
      directly above the real "Table 15" with the same caption
