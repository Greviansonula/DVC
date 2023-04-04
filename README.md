# Data Version Control

## Commands

dvc init

dvc add weather-data/2006-04-10.csv


dvc run --force \
-n filter \
-d filter.py -d weather-data/2006-04-10.csv \
-p filter.value \
-o output/filter \
python3 filter.py

dvc repro

dvc run --force \
-n training \
-p training.num_rows \
-d training.py -d output/filter -d weather-data/2006-04-10.csv \
-o output/training \
python3 training.py output/filter




dvc dag
