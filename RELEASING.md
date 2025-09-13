# Releasing the dataset

## Recreate the raw data from glottography-data

In case of upstream changes in glottography-data:
```shell
cldfbench download cldfbench_haynie2019modern.py
```

## Recreate the CLDF data

```shell
cldfbench makecldf cldfbench_haynie2019modern.py --glottolog-version v5.2
cldfbench cldfreadme cldfbench_haynie2019modern.py
cldfbench zenodo --communities glottography cldfbench_haynie2019modern.py
cldfbench readme cldfbench_haynie2019modern.py
```

## Validation

```shell
cldf validate cldf
```

```shell
cldfbench geojson.validate cldf
```

```shell
cldfbench geojson.glottolog_distance cldf --format pipe
```

```shell
cldfbench geojson.glottolog_distance cldf --format tsv | csvformat -t | csvgrep -c Distance -r"^0\.?" -i | csvsort -c Distance | csvcut -c ID,Distance | csvformat -E | termgraph
```

```
cree1270: ▇▇▇▇▇ 1.01 
sanf1262: ▇▇▇▇▇ 1.01 
sius1254: ▇▇▇▇▇ 1.09 
coah1252: ▇▇▇▇▇ 1.10 
eude1234: ▇▇▇▇▇▇ 1.16 
adai1235: ▇▇▇▇▇▇ 1.18 
matt1238: ▇▇▇▇▇▇ 1.18 
sars1236: ▇▇▇▇▇▇ 1.22 
yaqu1251: ▇▇▇▇▇▇ 1.28 
jica1244: ▇▇▇▇▇▇▇ 1.48 
moni1237: ▇▇▇▇▇▇▇ 1.48 
otta1242: ▇▇▇▇▇▇▇▇ 1.62 
east2695: ▇▇▇▇▇▇▇▇ 1.68 
wiyo1248: ▇▇▇▇▇▇▇▇▇ 1.74 
arap1274: ▇▇▇▇▇▇▇▇▇ 1.86 
wamp1249: ▇▇▇▇▇▇▇▇▇▇ 1.91 
nask1242: ▇▇▇▇▇▇▇▇▇▇ 1.93 
chey1247: ▇▇▇▇▇▇▇▇▇▇▇ 2.07 
nawa1259: ▇▇▇▇▇▇▇▇▇▇▇ 2.22 
okan1243: ▇▇▇▇▇▇▇▇▇▇▇ 2.24 
plai1258: ▇▇▇▇▇▇▇▇▇▇▇▇ 2.33 
ston1242: ▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.49 
pawn1254: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.67 
kick1244: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.79 
pota1247: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 3.62 
mesk1242: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 4.02 
koas1236: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 6.13 
alab1237: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 6.85 
aleu1260: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 8.42 
ofoo1242: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 9.41 
```