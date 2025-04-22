## Installation

python version: 3.10.12

create "dataset" folder and place arcsite floor plan dataset "coco_512_keep_ratio" under it

```
virtualenv env
source env/bin/activate
pip install --upgrade pip
pip install -r requirements.txt 
pip install ipykernel

cd samples/arcsite/
python floorplan.py train --dataset=dataset/coco_512_keep_ratio,dataset2/coco_512_keep_ratio --weights=coco
```

## Run Jupyter notebooks

Open the `inspect_floorplan_data.ipynb` or `inspect_floorplan_model.ipynb` Jupter notebooks. You can use these notebooks to explore the dataset and run through the detection pipelie step by step.

## Train the floorplan model

Train a new model starting from pre-trained COCO weights

```
python floorplan.py train --dataset=dataset/coco_512_keep_ratio --weights=coco
```

Resume training a model that you had trained earlier

```
python3 floorplan.py train --dataset=dataset/coco_512_keep_ratio --weights=last
```

- The code in `floorplan.py` is set to train for 60K steps (30 epochs of 2000 steps each), and using a batch size of 4. Update the schedule to fit your needs.
