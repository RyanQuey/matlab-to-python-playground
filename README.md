# install octave
(I think this is only necessary if we want to write to Matlab also, or use oct2py)

```
sudo apt-get -y install octave
```

# install dependencies
(I think this is only necessary if we want to write to Matlab also, or use oct2py)
```
pip3 install -r requirements.txt
```

# if don't have it already, get Apache Zeppelin and Spark too (I'll leave that to you)
If using Datastax Cassandra, and it's in a directory on your home folder along with zeppelin: 
```
$HOME/dse-6.8.0/bin/dse cassandra -k -s
$HOME/dse-6.8.0/bin/dse exec ~/zeppelin/bin/zeppelin.sh
```

NOTE make sure to also get the Matlab Playground notebook from https://github.com/RyanQuey/dse-zeppelin-notebooks.git

# View your data on Zeppelin

http://localhost:8080/#/

# Things to check out
- Integration between oct2py and ipython: see [octavemagic](https://nbviewer.jupyter.org/github/blink1073/oct2py/blob/master/example/octavemagic_extension.ipynb?create=1)
- Read .mat files using oct2py: https://stackoverflow.com/questions/45525233/loading-mat-and-m-files-with-loadmat-in-python

