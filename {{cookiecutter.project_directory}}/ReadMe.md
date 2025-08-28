# {{cookiecutter.project_name}}

This is the repository of the codes, data, reports and files for "{{cookiecutter.project_name}}" project with a team composed of "{{cookiecutter.project_team}}".

{{cookiecutter.project_description}}

Please read below about the folder structure and what is stored where. Please follow this structure as far as possible and keep the root folder clean :) thank you!

To contact, use this email address: {{cookiecutter.contact_email}}

## Folder structure of "{{cookiecutter.project_name}}" project

### **code/**

This includes Python, R, SQL, and any other language scripts and replication codes. Please use two digit numbers to indicate the order of operations e.g., "00", "01", "02" etc. If it is better to create sub-folders, please feel free to do so.

### **inputs/**

This folder includes "raw" data files.

Please do not modify this folder's contents and only "read" them with your scripts. Modified data files should be saved in the "outputs" folder (below). If you want to add new data files from other sources to be merged with bibliometric data, please include the "raw" version here and processed version in "outputs" folder. Thanks. **Please note that this bibliometric data should not be moved outside MPIDR's computing server (this folder and machine)**.

### **outputs/**

This is similar to "inputs" folder but includes "processed" and "modified" data files. Your scripts in "code" folder should read the data in "inputs" and store modified version of them inside this folder, i.e., "outputs".

### **literature/** or better, use a Zotero group library

This is for the reading materials that were shared previously. I would recommend creating a shared (free) Zotero group library that allows citing and creating bibliographies. That will make writing process easier by exporting ".bib" file of references and using them in latex or other text processing tools like MS Word.

### **writing_latex_backup/**

We will use ShareLatex/Overleaf to write a manuscript as the final output of project. Once in a while, we need to export the source files from ShareLatex/Overleaf and copy them here so that in case of technical failure, we do not lose all our previous work.

Alternatively, one of us can use the "git" integration in ShareLatex/Overleaf and pull a clone of it here and once a while pull again.

### **other/**

Other files that do not fit the above categories go here. For instance, "meeting notes" could be here. Consent forms to use licensed bibliometric data are included here as well. **Please note that this bibliometric data should not be moved outside MPIDR's computing server (this folder and machine)**.

### **workflow_w_snakemake/**

This folder includes an example workflow with `SnakeMake` workflow management tool. It includes a complete folder structure and example scripts and rules, i.e., steps in analysis, outlined in Snakefile.

### **ReadMe.md**

This file which describes the folder structure and how to use them.
