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

### Phase 3

The original `group3` data in `sas` folder was processed with the `cl_st1_ph3_gelc.sas` programme in `SAS OnDemand for Academics`. However, the results did not match with the original results of `group3`. Probably, the SAS programme that had previously processed the statistical procedures for `group3` is not exactly the same one that is being currently adopted - we know there has been a change from `PREROTAT` to `PATTERN`.

As a result, the examples that were obtained did not match the original examples for `group3`.

### Phase 4

The original results of the statistical procedures for `group3` were processed by the `examples` function in `lmda.sh`.

Original `examples_f1_pos_000001.txt`

```
file = t016771
date = 2022-11-00
user = url:https://twitter.com/mpatriabrasil/status/1595992165557178400
conversation = 99999999
URL = 

word count = 46
words loading = 13
factor score = 12

Mais **jovens** **falecendo** por **infartos** e **males** **Súbitos** . É 
importante lembrar que a **pesquisa** científica da @CMAJ, **publicada** nesta 
**semana** , **indicou** q o **risco** d problemas **cardíacos** é d 100 p / 
cada 100mil **doses** . É duro saber que estes **morreram** p / q alguns se 
sentissem seguros. . . https://t.co/xFSmndVjej 

Lemmas in this text that loaded on the factor:

cardíaco
dose
falecer
indicar
infarto
jovem
mal
morrer
pesquisa
publicar
risco (secondary)
semana
súbito
```

Obtained `examples_f1_pos_000001.txt`

```
file = t016771
date = 2022-11-00
user = mpatriabrasil
conversation = 99999999
URL = https://twitter.com/mpatriabrasil/status/1595992165557178400

word count = 46
words loading = 11
factor score = 12

Mais **jovens** **falecendo** por **infartos** e **males** Súbitos. É 
importante lembrar que a **pesquisa** científica da @CMAJ, **publicada** nesta 
**semana** , **indicou** q o **risco** d problemas cardíacos é d 100 p / cada 
100mil **doses** . É duro saber que estes **morreram** p / q alguns se 
sentissem seguros. . . https://t.co/xFSmndVjej 

Lemmas in this text that loaded on the factor:

dose 
falecer 
indicar 
infarto 
jovem 
mal 
morrer 
pesquisa 
publicar 
risco (secondary)
semana 
```

Original `examples_f1_neg_000035.txt`

```
file = t000907
date = 2020-10-30
user = url:https://twitter.com/FabioIng/status/1321947496466272258
conversation = 81842196
URL = 

word count = 25
words loading = 4
factor score = -2

" @JornalDaCidadeO @VlogdoLisboa - Hidroxicloroquina. Há 70 anos no **mercado** 
: " " não tem **comprovação** científica, é perigoso " " - Vacina. Feita em 7 
meses: " " deve ser obrigatória. " " **Dama** de **ferro** / TT " 

Lemmas in this text that loaded on the factor:

comprovação
dama
ferro
mercado
```

Obtained `examples_f1_neg_000035.txt`

```
file = t000907
date = 2020-10-30
user = FabioIng
conversation = 81842196
URL = https://twitter.com/FabioIng/status/1321947496466272258

word count = 25
words loading = 3
factor score = -2

" @JornalDaCidadeO @VlogdoLisboa - Hidroxicloroquina. Há 70 anos no 
**mercado** : " " não tem comprovação científica, é perigoso " " - Vacina. 
Feita em 7 meses: " " deve ser obrigatória. " " **Dama** de **ferro** / TT " 

Lemmas in this text that loaded on the factor:

dama 
ferro 
mercado 
```

Findings:

- The obtained `factor score` matches the one of the original example
- The obtained `lemmas`, `words loading` and `words highlight` do not match with the ones of the original example - there are missing lemmas; 
- The `lemmas`, `words loading` and `words highlight` are aligned among each other.
