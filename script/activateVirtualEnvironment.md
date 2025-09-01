# Initial Installation

- Open a terminal in the folder that you want to create the project in
- Type ``'which python'`` or ``'which python3'`` to check Python is installed (Mac)
- Type ``'where python' (Windows)``

- Setup a Python virtual environment by typing the below, this will setup and activate a new virtual environment.

``python -m venv wikiVirtualEnvironment\``
``.\wikiVirtualEnvironment\Scripts\activate``

- Check pip version ``'pip --version'``

- Install mkdocs material - ````'pip install mkdocs-material'````

- Open Visual studio code in this folder with ``'code .'``

- Open a terminal within Visual Studio code

- Activate the virtual environment on the new terminal with ```source venv/bin/activate```

- Create a new site 
```ruby
mkdocs new . 
```

- Add the following basic configuration to the YAML file 
```ruby
mkdocs.yml
``` 

```ruby
mkdocs.yml

site_name: FKI Sags- & Dokument Indeks Documentation presented  MkDocs Material 
site_url: https://sitename.example
theme:
  name: material
```

- Type the following below to launch the site

```ruby
mkdocs serve
```

- Check the site at http://localhost:8000