# LogicNLG
The data and code for ACL2020 paper "Logical Natural Language Generation from Open-Domain Tables"


## Preparation
### Download the NLI scorer
```
wget https://logicnlg.s3-us-west-2.amazonaws.com/NLI_models.zip
unzip NLI_models.zip
```
### Download the Semantic Parser
```
wget 
```

## Evaluation Command
### Compute SP-ACC score
```
CUDA_VISIBLE_DEVICES=0 python parse_programs.py --compute_score --load_from parser_models/parser_step49161_acc0.58.pt --score_file outputs/[Your_File]
```
### Compute NLI-ACC score
```
CUDA_VISIBLE_DEVICES=0 python NLI.py --model bert-base-multilingual-uncased --do_verify --encoding gnn --load_from NLI_models/model_ep4.pt --fp16 --verify_file outputs/[Your_File] --verify_linking data/test_lm.json
```

## Parsing Command
```
python parse_programs.py --parse --score_file outputs/[Your_File]
```
