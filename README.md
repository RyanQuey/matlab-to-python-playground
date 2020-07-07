Notebook and environment for doing ETL on Matlab (`.mat`) files. 

Sample data taken from a dataset to supplement an article on ["EMG and data glove dataset for dexterous myoelectric control"](https://data.ncl.ac.uk/articles/EMG_and_data_glove_dataset_for_dexterous_myoelectric_control/9577598/1), originally for the purpose of aiding research into myoelectric prosthetics by means of machine learning. Particularly we focused on `S12_E1_A3.mat` due to its ideal sample size and since subject 12 is a right hand amputee. Information for data files is provided at `./data-files/Ninapro_DB8_SubjectsInformation.csv`, though of course the original article describes it more expressively.

This notebook extracts data from a `.mat` into Apache Spark (specifically using pyspark), and transforms it so the data is useable for drawing conclusions and noticing patterns and anomalies.

![image](https://github.com/RyanQuey/matlab-to-python-playground/raw/master/screenshots/zeppelin-notebook-matlab-demo.png)


## Setup Instructions
### Download sample data files, 
Click [here](https://data.ncl.ac.uk/ndownloader/files/17218115) and move file to wherever you want. But you'll need to have it accessible from the notebook. 

TODO Have users put it in this directory, and then point the notebook path to here, and add it to .gitignore

### Install octave
(I think this is only necessary if we want to write to Matlab also, or use oct2py)

```
sudo apt-get -y install octave
```

### Install dependencies
(I think this is only necessary if we want to write to Matlab also, or use oct2py)
```
pip3 install -r requirements.txt
```

### if don't have it already, get Apache Zeppelin and Spark too (I'll leave that to you)
If using Datastax Cassandra, and it's in a directory on your home folder along with zeppelin: 
```
$HOME/dse-6.8.0/bin/dse cassandra -k -s
$HOME/dse-6.8.0/bin/dse exec ~/zeppelin/bin/zeppelin.sh
```

NOTE make sure to also get the Matlab Playground notebook from https://github.com/RyanQuey/dse-zeppelin-notebooks.git

## View your data on Zeppelin

http://localhost:8080/#/

## Things to check out
- Integration between oct2py and ipython: see [octavemagic](https://nbviewer.jupyter.org/github/blink1073/oct2py/blob/master/example/octavemagic_extension.ipynb?create=1)
- Read .mat files using oct2py: https://stackoverflow.com/questions/45525233/loading-mat-and-m-files-with-loadmat-in-python

# Released under MIT License

Copyright (c) 2020 Ryan Quey.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
