# cl_st1_gelc

## Corpus Linguistics - Study 1 - GELC

- Lexical Multi-Dimensional Analysis

### Phase 1

Aimed at validating the current software baseline.

- Using the original `tweets/tagged.txt`.

Findings:

- `tokens.txt` and `tokens_ori.txt` are identical;
- `types.txt` and `types.txt` are similar - the order of types vary in some of the lines;
- `selectedwords` and `selectedwords_ori` are similar - there are changes in the order of variables but the variables themselves remain the same;
- The files in `sas` and `sas_ori` are similar.

### Phase 2

Introduces variation due to the tagging process.

- Using the original `tweets/emoji.txt` renamed to `tweets/tweets.txt`.

Findings:

- Running the tagging process twice results in identical `tagged.txt` files, therefore the processing is deterministic;
- `tokens.txt` and `tokens_ori.txt` bear differences;
- `types.txt` and `types.txt` bear differences;
- `selectedwords` and `selectedwords_ori` bear differences;
- The files in `sas` and `sas_ori` bear differences.

The findings indicate that the differences in the tagging process are not trivial.

There should not have been reason for the difference in tagging results since TreeTagger has been configured with the same parameter file for Portuguese - `portuguese2.par`.
