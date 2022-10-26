## Examples of the general use of ``premise``
https://github.com/polca/premise/blob/master/examples/examples.ipynb

## Examples of the use of ``premise`` with user-made scenarios
https://github.com/polca/premise/blob/master/examples/examples%20user-defined%20scenarios.ipynb

## ``premise`` general documentation
https://premise.readthedocs.io/en/latest/

## ``premise`` documentation on the use of user-made scenarios
https://premise.readthedocs.io/en/latest/user_scenarios.html

## ``premise`` on GitHub
https://github.com/polca/premise/tree/master/premise

## ``premise`` decryption key
```
key = 'tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo='
```

## General requirements

- ``python`` >= 3.9
- ``bw2io 0.8.7``
- a ``brightway2`` project with the ecoinvent >=3.5 cutoff database

## Install ``premise`` from PyPI
```
pip install premise
```

## Install ``premise`` from Conda
```
conda config --append conda-forge
conda config --append cmutel
conda config --append romainsacchi
conda install premise
```

## Install ``premise`` from GitHub
```
pip install git+https://github.com/polca/premise.git
```

## A few advices on using ``premise``

- ``premise`` is a package that is still under development. 
It may present some errors. In which case, report them to Romain Sacchi.

- if you intend to run several years of a same scenario 
(e.g., "SSP2-RCP6" from 2005 to 2050 by time step of 5 years), 
you may want to consider export the scenarios as a 
superstructure database (`ndb.write_db_to_superstructure("my_db")`) 
and then run the analysis using Activity-Browser. This allows to only
write one database to disk.

- for the above case, it is better to install and run ``premise`` on 
your computer, in a conda environment, not the school server.

- running ``premise`` on the school server is possible, but it is
difficult to fetch log files, which cna be pretty useful (especially when 
creating user scenarios).

- before writing a database to disk, you can check if it looks the way
you want it to look by accessing from the RAM. For example,:

```
temp_db = ndb.scenarios[0]["database"]

for act in temp_db:
    for exc in act["exchanges"]:
        if exc["type"] == "technosphere":
            print(act["name"], exc["name"])
```
