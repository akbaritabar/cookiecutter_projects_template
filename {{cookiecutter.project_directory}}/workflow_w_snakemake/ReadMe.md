# This a reproducible workflow using SnakeMake for project {{cookiecutter.project_name}}

This is the reproducible workflow using SnakeMake including the codes, data, reports and files for "{{cookiecutter.project_name}}" project with a team composed of "{{cookiecutter.project_team}}".

{{cookiecutter.project_description}}

Please read below about SnakeMake and how to replicate the analysis pipeline.

To contact, use this email address: {{cookiecutter.contact_email}}

## Note on installation

If you build your vanilla python environment using the `requirements.txt` that I provided in this directory, `uv` (or alternatively `pip`) is going to install duckdb, SnakeMake, and their dependencies. 

## Folder structure of {{cookiecutter.project_name}} project

### **config/**

This folder stores configuration files used by the workflow, such as `config.py` for central parameters and settings.

### **docs/**

This folder contains documentation artifacts of the workflow. For example, `DAG.html` shows the Directed Acyclic Graph representation of pipeline dependencies.

### **logs/**

This folder stores log files generated during workflow execution. Use it to inspect run status, warnings, and errors.

### **other/**

This folder is for supplementary files that do not clearly belong to code, resources, results, or documentation.


### **resources/**

This folder includes raw input files that we use in the workflow and its scripts to generate outputs and figures (next section).

### **results/**

This folder contains workflow outputs produced by Snakemake rules. Subfolders such as `figures/`, `tables/` could go here.

### **workflow/**

This folder contains the executable pipeline definition and code. The `Snakefile` defines rules and dependencies, while `scripts/` includes Python, R, bash and similar scripts used by those rules.

### **ReadMe.md**

This file explains the purpose of this reproducible Snakemake workflow, how to run it, and what each folder contains.

# What is SnakeMake?

SnakeMake is a workflow management tool. It allows you to set up your reproducible data analysis pipeline by thinking about `input`, `output`, and the `script` which generates the output from the input.

With those three elements, you do not need to think about the dependency between steps, SnakeMake will do that for you as it understands which output is then used by the next steps as input and creates a dependency graph in form of a Directed Acyclic Graph (DAG). You can use SnakeMake's inbuilt tool to visualize this DAG and see if the logic makes sense? Additionally, SnakeMake will figure out if any step could be done in parallel to the others and take care of the parallelization. You can decide and provide the amount of recourses such as number of CPU cores it can use. Please check SnakeMake's wealth of tutorial, videos, example repositories and catalogue for more information [https://snakemake.readthedocs.io/en/stable/](https://snakemake.readthedocs.io/en/stable/).

It works with R, Python, Julia, bash and similar scripts and applies the above logic on all of these tools. For instance, your project could have a few steps on data processing done in bash, the next steps in Python and the final statistical modelling and visualization in R and SnakeMake will orchestrate these to play nicely with each other.

## How to follow the example scripts? 

Note that SnakeMake is a command line tool. Please note that while you can use SnakeMake in interactive mode using for instance Jupyter notebooks, R, Python etc. scripts. However, it is much easier to set your scripts up and then use SnakeMake as a command line tool to run everything. See the next section for a more advanced example of this.

After creating the virtual environment using the provided `requirements.txt`, you can open a Powershell or command prompt on Windows or terminal, activate this virtual environment (see hands-on directory's ReadMe) and do `snakemake --version` which should print out a number or `snakemake --help` which should print out a long list of arguments and commands that gives you a lot of freedom to design your workflow and manage it. As of today, July 6, 2025, and for the version `9.5.1`, this help is similar to the one in file `snakemake_help.md` (open it with a text editor).

Since I suggested to use `uv` to create the environment and install requirements, you would do `uvx snakemake --version` to run snakemake using uv's created environment. Now to run the workflow that I have shared, in the terminal, you can activate the virtual environment, e.g., by doing `.\.venv\Scripts\activate.ps1` on Windows Powershell, and do `snakemake -np all` which is a `dry-run` in SnakeMake lingua. This will NOT run any codes in your pipeline, but it will check everything and report back if something is wrong in syntax, requirements etc.

When you are sure all is well and ready, you can do `snakemake --cores 4 all` which allocates 4 CPU cores to snakemake to run the rule `all` which is defined on the top of Snakefile to collect all outputs of different steps.

# Where to see a more advanced example?

In this repository, you can find an example reproducible workflow with data and scripts using SnakeMake: [https://github.com/akbaritabar/Internal-and-international-migration-of-scientists](https://github.com/akbaritabar/Internal-and-international-migration-of-scientists) which are replication materials of the following publication:

```
Akbaritabar, A., Dańko, M. J., Zhao, X., & Zagheni, E. (2025). Global subnational estimates of migration of scientists reveal large disparities in internal and international flows. Proceedings of the National Academy of Sciences, 122(15), e2424521122. https://doi.org/10.1073/pnas.2424521122

```