# Validation Data — A Bulletproof Business? Towards Detecting Infrastructure-as-a-Service Offerings on Telegram

This repository is provided for double-blind peer review and contains no author-identifying information.

It holds the human-annotated samples behind the classifier validation reported in the paper (Section 3.2.2 and Appendix G). Each file is a sample of Telegram messages together with independent human labels, classifier predictions, or both, following the taxonomy and codebook defined in the paper's Appendix C.

## Infrastructure Detection Tool — Keyword and TF-IDF + Logistic Regression Methods

File `reproducible_infrastructure_labeling.ipynb` has the code for the tools tested and the final one utilized. 

## Taxonomy inter-annotator agreement — Table 7

| File | Contents |
|---|---|
| `annotator_1_taxonomy_validation.xlsx` | Labels from the first of two independent coders on the 250-message stratified validation sample (§3.2.2), covering all six infrastructure categories and three trust attributes. |
| `annotator_2_taxonomy_validation.xlsx` | Labels from the second coder on the same 250-message sample. Together with the file above, these two are the basis for the Cohen's kappa reported in Table 7. |

## External classifier validation — infrastructure categories (Appendix G.1–G.3)

| File | Contents |
|---|---|
| `labelled_domain_transfer_validation.xlsx` | 100 messages predicted as infrastructure by the classifier, drawn from communities outside the 11 used for taxonomy development and training. Independently annotated to assess precision under domain shift (Appendix G.1, Table 10). |
| `labelled_predicted_infrastructure_validation.xlsx` | 50 messages predicted as infrastructure by the classifier, drawn from the training domain. Independently annotated to assess in-domain precision (Appendix G.2, Table 11). |
| `labelled_predicted_noninfrastructure_validation.xlsx` | 50 messages predicted as non-infrastructure by the classifier (all six categories negative). Independently annotated to estimate the false-negative rate (Appendix G.3, Table 12). |

## External classifier validation — trust attributes (Appendix G.4)

| File | Contents |
|---|---|
| `trust_validation_sample_with_predictions.xlsx` | 100 unique messages, stratified across the classifier's predicted-positive pool for each trust attribute (Bulletproof, Payment security, Transparency), with model predictions and the stratum each message was drawn for. |
| `trust_validation_for_annotation_completed.xlsx` | The same 100 messages with predictions hidden, independently annotated by hand for the three trust attributes. Comparing this file with the one above reproduces the validation metrics in Appendix G.4. |
