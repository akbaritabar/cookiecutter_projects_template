# How to use project templates?

My usual practice is to create a Python virtual environment, then install cookiecutter and use it to create new project directories with this template. Those projects of course will have their own Python, R, etc. requirements that needs to be installed afterwards to use.

## Steps to use the template

1. Open a terminal
2. Install vanilla Python from: [https://www.python.org/](https://www.python.org/)
   1. See [my guidelines on using Pyenv](https://github.com/akbaritabar/course-session-on-Other-Computational-Social-Science-Skills/tree/main/Hands_on)
3. Create a folder e.g., `projectTemplates` and use `Virtualenv` to create `env` inside it with `python -m virtualenv env`, activate it with `.\Scripts\activate.bat` (on Windows), and install the requirements, i.e., `python -m pip install -r requirements.txt`
4. Then cd to 'C:\projectTemplates' which is now a vanilla Python environment created for cookiecutter templates using the 'requirements.txt' file in this directory (which simply includes cookiecutter. I also included the data science template, that could be useful but is more elaborated than what I needed).
5. To use the GitHub version of my own template, do `cookiecutter 'https://github.com/akbaritabar/cookiecutter_projects_template'`
6. Answer the questions asked and it will create a project in your terminal's working directory using this template. It will include all the files and ReadMe items which now are populated using your answers to the questions about the project.
7. Create a virtual environment for Python and install requirements as I wrote above (See [my guidelines on using Pyenv](https://github.com/akbaritabar/course-session-on-Other-Computational-Social-Science-Skills/tree/main/Hands_on)) and enjoy!
