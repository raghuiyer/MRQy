![Picture1](https://user-images.githubusercontent.com/50635618/77593997-b1492a00-6ecb-11ea-939c-c8962f371e5a.png)

## Front-end View
![gbm_mrqy](https://user-images.githubusercontent.com/50635618/77496601-b6519f00-6e21-11ea-8f52-16f33d4c66cc.gif)

## Backend View
![gbm_mrqy](https://user-images.githubusercontent.com/50635618/77506445-43095680-6e3c-11ea-9376-7be6f7cdc5d8.gif)



# Table of Contents
- [Description](#description)
- [Prerequisites](#prerequisites)
- [Running](#running)
- [Basic Information](#basic-information)
  * [Measurements](#measurements)
  * [User Interface](#user-interface)
- [Feedback and usage](#feedback-and-usage)





## Description


This tool takes MRI datasets in the file formats (_.dcm_, _.nii_, _.nii.gz_ or _.mha_) as the input. \
Two Python scripts (_QC.py_ and _QCF.py_) are used to generate several tags and noise/information measurements for quality assessment. These scripts save the calculated measures in a  _.tsv_ file as well as generate _.png_ thumbnails for all images in a subject volume. These are then fed to _.js_ scripts to create the user interface (_index.html_) output. A schematic illustrating the framework of the tool is as follows.



![Picture1](https://user-images.githubusercontent.com/50635618/76675455-07df6b80-6590-11ea-85f7-13b71a9a1ec3.png)





## Prerequisites

The current version of the tool has been tested on the Python 3.6+  
You must have [pipenv](https://pipenv-fork.readthedocs.io/en/latest/basics.html) installed on your environment to run MRQy locally. It will pull down all the dependencies listed in the diagram.

![Picture7](https://user-images.githubusercontent.com/50635618/76580525-a2638000-64a6-11ea-8a37-38e95c4693c3.png)

## Running

For local development, test that the code is functional
```
MRQy % pipenv shell
(mrqy) MRQy% pipenv install .
(mrqy) MRQy% python -m mrqy.QC --help

```
The output should be 
```
usage: QC.py [-h] output_folder_name [inputdir [inputdir ...]]

positional arguments:
  output_folder_name  the subfolder name on the
                      '...\UserInterface\Data\output_folder_name' directory.
  inputdir            input foldername consists of *.mha (*.nii or *.dcm)
                      files. For example: 'E:\Data\Rectal\input_data_folder'

optional arguments:
  -h, --help          show this help message and exit
  
```
Standard usage is to run ``` QC.py output_folder_name “input directory” ``` i.e. 

```
python QC.py output_folder_name "E:\Data\Rectal\RectalCancer_Multisite\input_data_folder"

```
There is no need to make a subfolder in the Data directory, just specify its name in the command like above code line.\
Every action will be printed in the output console. \
The thumbnail images in the format of _.png_ will be saved on "...\UserInterface\Data\output_folder_name" with its original filename as its subfolder's name. Afterward, double click "index.html" (on e.g. "D:\Downloads\MRQy-master\UserInterface") to open front end user interface, select the respective _results.tsv_ file from the e.g. "D:\Downloads\MRQy-master\UserInterface\Data\output_folder_name" directory.

## Contribution guidelines

### Testing

```
MRQy % pipenv shell
(mrqy) MRQy% pipenv install .
(mrqy) MRQY% pipenv run -m pytest tests/
```

### Building on Travis
The recommended path is to follow the [Forking Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow). Create a Travis CI build for your github fork to validate your fork before pushing a merge request to master.


## Basic Information 

### Measurements

The measures of the MRQy tool are listed in the following table.

![Picture1](https://user-images.githubusercontent.com/50635618/76733243-cb9a3f80-6736-11ea-8100-a1bdb6f60d3f.png)


### User Interface

The following figures show the user interface of the tool (index.html). 

![C1](https://user-images.githubusercontent.com/50635618/78467306-3ce76580-76d9-11ea-8dbd-d43f82cd29a6.PNG)
![C2](https://user-images.githubusercontent.com/50635618/78467302-3bb63880-76d9-11ea-84ff-ce44f5f8a822.PNG)
![C3](https://user-images.githubusercontent.com/50635618/78467305-3ce76580-76d9-11ea-96a8-7574042c14c6.PNG)

## Feedback and usage

Please report and issues, bugfixes, ideas for enhancements via the "Issues" tab

You can cite this in any associated publication as:  
Sadri, AR, Janowczyk, A, Zou, R, Verma, R, Antunes, J, Madabhushi, A, Tiwari, P, Viswanath, SE, "MRQy: An Open-Source Tool for Quality Control of MR Imaging Data", https://arxiv.org/abs/2004.04871v2, 2020

If you do use the tool in your own work, please drop us a line to let us know.
