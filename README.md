# myproject 

myproject is a simple shell script to automatically create folders and files according to the type of project. 

At the moment, it only supports YouTube projects, however, the goal is to have custom templates that can be applied and according those templates, the directory structure will be created. 

As it is, the script does not do any kind of error checking. 

## Installation

Navigate inside the myproject source code folder. 

`sudo bash install.sh`

## Usage

### youtube

#### create project

Navigate to the folder you would like to add project files to.

`myproject add youtube project <project_name>`

`<project_name>` must not contain spaces or special characters

This will create the directory structure as follows: 

##### directory structure

.:
audio  project.md  script  video

./audio:
edits  recordings  renders

./script:
master.md

./video:
edits  recordings  renders

#### add scene


`myproject add youtube scene <scene_name>`

`<scene_name>` must not contain spaces or special characters

- This command will create folders:
	- `./video/recordings/<scene_name>`
	- `./audio/recordings/<scene_name>`
- create a script file `./script/<scene_name>.md`
- add path to `<scene_name>`.md in `script/master.md`
- add links to the folders and files created above in `./project.md`

### software 

#### create project

Navigate to the folder you would like to add project files to.


`myproject add software project <project_name>`

`<project_name>` must not contain spaces or special characters

This will create the directory structure as follows: 


##### directory structure

.:
bugs  config  features  project.md  tests  wiki

#### add [bug|test]


`myproject add software bug <bug_name>`
`<bug_name>` must not contain spaces or special characters

- This command will: 
	- create bug file or test file with the given name 
	- add a link in project.md under bugs or tests respectively

You can then open `./project.md` in vim and get access to all the files and folders in the projects from one place via the default  netrw file browser. 
