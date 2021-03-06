# ONEPANEL-CLI ver. 2.12.16

## INSTALLATION
```
pip install -UI onepanel
```

## USAGE  
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
  - after users logs in, user will be able to check available projects with cli
  - while logged in users can also create, delete, clone projects / workspaces / datasets under their account with cli
  - users can push changes to repository by using 'onepanel push' command.
  - users also has access to jobs for parallel training, for more info about jobs please go to JOBS article

**LOGOUT**  
Logs the user out of session

**PROJECTS**  
Projects are the highest level container and are the first thing you will need to create to get started.  
[https://help.onepanel.io/projects/creating-projects/creating-projects](https://help.onepanel.io/projects/creating-projects/creating-projects)
```
Commands:
  create  Create project in new directory.
  init    Initialize project in current directory.
  list    Display a list of all projects.
```

**DATASETS**  
Users can create datasets from local machine using the command <onepanel datasets create 'dataset_name'> or initiate a folder as a dataset by using <onepanel datasets init> then running <onepanel push> to push in account dataset repository.  
Datasets are version controlled containers that can store more than 100Gb of data(can either be images or text files)
 - Datasets use AWS and git-lfs to store data, for full guide with AWS please click this [link.](https://help.onepanel.io/datasets/creating-datasets-from-aws-s3)  
[https://help.onepanel.io/datasets/creating-datasets](https://help.onepanel.io/datasets/creating-datasets)
```
Commands:
  create  Create dataset in new directory.
  init    Initialize dataset in current directory.
  list    Display a list of all datasets.
  pull    Pull down dataset and any changes
  push    Push up dataset changes
```

**JOBS**  
User can create / run jobs with CLI.  
Jobs are great for testing different aspects of a model (i.e., training on different versions of a dataset for a model that may include different labeling parameters).  
Job command chaining is also available, you can find more information thru this [link](https://help.onepanel.io/jobs/job-command-chaining)  
Jobs also provides visualizations while training with Tensorboard. For full guide you can refer to this [link](https://help.onepanel.io/jobs/tensorboard-visualizations-in-jobs)  
Jobs can run in parallel which means:
  - users can run training at the same time with different environments, this way users can assess which environment suits the model for better performance
  - jobs trained in parallel can have different parameters, this greatly helps hasten users find the best model when training, specially with large datasets.
  - this also provide output files while training(if checkpoints are added to code) and after training.  
  To save your models and any other output, save your data to /onepanel/output.  
  For full guide please refer to this [link](https://help.onepanel.io/jobs/job-output)  


**Note:** Jobs can only execute code that is committed into the "Code" repository.  
[https://help.onepanel.io/jobs/creating-jobs](https://help.onepanel.io/jobs/creating-jobs)
```
Options:
  -m, --machine-type TEXT         Machine type ID. Call "onepanel machine-
                                  types list" for IDs.  [required]
  -e, --environment TEXT          Instance template ID. Call "onepanel
                                  environments list" for IDs.  [required]
  -s, --storage TEXT              Storage type ID.  [required]
```

**WORKSPACES**  
Workspaces are version controlled docker instances that can contain source code, libraries & dependencies, and environment settings.    
You can also collaborate on workspaces with other users by adding members to your project.
[https://help.onepanel.io/workspaces/creating-workspaces](https://help.onepanel.io/workspaces/creating-workspaces)
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
Below are all the available environment Onepanel can provide, from Tensorflow to H2O, users have a variety of options to use when creating models or scripts for their project, these are all available with both workspaces and jobs.  
for information with pricing for types of environment you can refer to this [link](https://www.onepanel.io/pricing#compute-storage-pricing)
```
Commands:
  list  Show available environments
  
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
Volume-types provides users information as to how much storage they can use when they run workspaces for their projects, this can either be used for datasets, large data files, images, etc.  
for information with pricing for different SSD volumes you can refer to this [link](https://www.onepanel.io/pricing#compute-storage-pricing)
```
Commands:
  list  Show available volume types and their IDs

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
**MACHINE-TYPES**  
Machine type command provides user an overview for available CPU/GPU machines that Onepanel can provide, together with how much they are billed in a hour basis.
```
Commands:
  list  Show available machine types
  
 ID              SPECS
 cpu-2-8         CPU: 2, RAM: 8GB ($0.112/hr)
 cpu-8-32        CPU: 8, RAM: 32GB ($0.446/hr)
 gpu-4-26-1k80   GPU: 1 (Tesla K80), CPU: 4, RAM: 26GB ($0.750/hr)
 gpu-8-52-1v100  GPU: 1 (Tesla V100), CPU: 8, RAM: 52GB ($3.226/hr) 
```
