# SyntaxGym Evaluation

This repository contains test suites and scripts for evaluating syntactic generalization in neural language models. The code is based on [SyntaxGym](https://github.com/cpllab/syntaxgym-core), with modification to support evaluation directly from model's surprisal output.

Required python packages may include `docker`, etc.

## Environment

This code requires Python 3.7. You can install the modules with `pip` as

    pip install numpy pandas docker tqdm pyparsing

## Preparing surprisal files

The evaluation script takes an surprisal file as its input. An example of the surprisal file can be found in the last section of [Quick Start page](https://cpllab.github.io/lm-zoo/quickstart.html) from LM-zoo documentation.

## Get accuracy score for a particular test suite

The following script will print out the score for the test suite `fgd_hierarchy.txt`

```
test_name="fgd_hierarchy"
SURPRISAL_PATH="examples/"
RESULT_PATH="item_specific_rs.txt"
> ${RESULT_PATH}
python score.py --surprisal ${SURPRISAL_PATH}/surprisals_${test_name}.txt --sentences test_suites/txt/${test_name}.txt --spec spec.template.json --input test_suites/json/${test_name}.json 2>>${RESULT_PATH}
```
The mean accuracy score will be printed out. By-item evaluation results will be in the file `${RESULT_PATH}`.

