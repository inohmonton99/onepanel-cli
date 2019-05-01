# ONEPANEL-CLI ver. 2.12.16

## Installation:
```
pip install -UI onepanel
```

**USAGE**  
```
Options:  
  --version  Show the version and exit.  
  --help     Show this message and exit.

Commands:  
  clone          Clone project or dataset from server.  
  datasets       Dataset commands group  
  download       Download a dataset  
  environments   Environment (machine types) commands group  
  jobs           Job commands group  
  login          Login with email and password.  
  logout         Logs the current user out.  
  machine-types  Machine (hardware) commands group  
  projects       Project commands group  
  pull           Pull changes from onepanel (fetch and merge)  
  push           Push changes to onepanel  
  volume-types   Available volume types  
  workspaces     Workspace commands group
 ```

**LOGIN**  
after installation, users should log in with valid credentials first via email and password

**LOGOUT**  
Logs the user out of session

**PROJECTS**  
[Onepanel CLI projects commands group](https://help.onepanel.io/projects/creating-projects/creating-projects)
```
Commands:
  create  Create project in new directory.
  init    Initialize project in current directory.
  list    Display a list of all projects.
```

**DATASETS**  
[Onepanel CLI datasets commands group](https://help.onepanel.io/datasets)
```
Commands:
  create  Create dataset in new directory.
  init    Initialize dataset in current directory.
  list    Display a list of all datasets.
  pull    Pull down dataset and any changes
  push    Push up dataset changes
```

**JOBS**  
[Onepanel CLI jobs commands group](https://help.onepanel.io/jobs/creating-jobs)
```
Commands:
  create  Execute a command on a remote machine in the current project
  delete  Delete a job
  list    Show commands executed on remote machines
  logs    Show a log of the command
  stop    Stop a job
```

**WORKSPACES**  
[Workspace commands group](https://help.onepanel.io/workspaces/creating-workspaces)
```
Commands:
  create            Create a new workspace.
  create-from-file  Create new workspaces from a json file.
  list              Show workspaces.
  pause             Pause the workspace(s) given the uids of the workspace
  resume            Resume the workspace(s) given the uids of the workspace
  terminate         Terminate the workspace(s) given the uids of the workspace
```

**ENVIRONMENTS**  
Commands:
  list  Show available environments
```
Output:
ID                              ENVIRONMENT
jupyter-py3-tensorflow1.11.0    Python 3, TensorFlow 1.11.0, Jupyter 5.6.0
jupyter-py3-pytorch1.0.0-rc.1   Python 3, PyTorch 1.0, Jupyter 5.6.0
jupyter-py3-tensorflow1.10.0    Python 3, TensorFlow 1.10.0, Jupyter 5.6.0
jupyter-py3-tensorflow1.9.0     Python 3, TensorFlow 1.9.0, Jupyter 5.6.0
jupyter-py3-tensorflow1.8.0     Python 3, TensorFlow 1.8.0, Jupyter 5.5.0
jupyter-py3-pytorch0.4.0        Python 3, PyTorch 0.4.0, Jupyter 5.5.0
jupyter-py3-pytorch0.3.1        Python 3, PyTorch 0.3.1, Jupyter 5.5.0
jupyter-py3-r3.4.3              Python 3, R 3.4.3, Jupyter 5.5.0
h2o3.20.0.1-py3                 Python 3, H2O 3.20.0.1
image-annotation-0.2.0          CVAT Annotation Tool, Jupyter 5.5.0
node-red-py3-r3.4.3-node0.18.7  R, Python 3, Node-RED
```

**VOLUME-TYPES**  
Commands:
  list  Show available volume types and their IDs
```
Output:
ID                     SPECS
 default-storage-10     10 GB SSD
 default-storage-20     20 GB SSD
 default-storage-40     40 GB SSD
 default-storage-60     60 GB SSD
 default-storage-80     80 GB SSD
 default-storage-100    100 GB SSD
 default-storage-200    200 GB SSD
 default-storage-400    400 GB SSD
 default-storage-600    600 GB SSD
 default-storage-1000   1 TB SSD
 default-storage-2000   2 TB SSD
 default-storage-5000   5 TB SSD
 default-storage-10000  10 TB SSD
```
