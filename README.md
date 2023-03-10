# ezconfiguration  
[![PyPI Latest Release](https://img.shields.io/pypi/v/ezconfiguration)](https://pypi.org/project/ezconfiguration/) 
[![Downloads](https://img.shields.io/pypi/dm/ezconfiguration)](https://pypi.org/project/ezconfiguration/)
[![Repo Size](https://img.shields.io/github/repo-size/datanooblol/ezconfiguration)](https://pypi.org/project/ezconfiguration/)
[![License](https://img.shields.io/pypi/l/ezconfiguration)](https://pypi.org/project/ezconfiguration/)
[![Release Date](https://img.shields.io/github/release-date/datanooblol/ezconfiguration)](https://pypi.org/project/ezconfiguration/)

## What is ezconfiguration?

**ezconfiguration** is a Python package for building a configuration file in an easy way.  

## Where to get ezconfiguration  
The source code is currently hosted at GitHub:  
https://github.com/datanooblol/ezconfiguration  

The latest version is available at  
[Python Package Index (PyPI)](https://pypi.org/project/ezconfiguration/)  

```sh  
# pip  
pip install ezconfiguration  
```  

## How to use ezconfiguration  

Steps to follow:
```python

# Import EzPackage
from ezconfiguration.config_manager import EzConfig

# Initialize EzConfig object
ezcfg = EzConfig(directory='your-desired-directory', filename='filename.json')

# Write a configuration file. If file already exists, replace=True
ezcfg.write_config_file(config_dict={"a":1})

# Read a configuration file. It's a good practice to use this method after writing, inserting, updating, deleting method.
ezcfg.read_config_file()

# Insert a new configuration. If a config already exists, replace=True
ezcfg.insert_config(config_dict={'b':[2,3,4]})

ezcfg.read_config_file()

# Update the existing configuration. Always replace=True
# Note: in the case when you want to update the nested configuration, use insert method with the whole nested config instead
ezcfg.update_config(key='a', value=5, replace=True)

ezcfg.read_config_file()

# Delete a configuration. Input delete config
ezcfg.delete_config(key='b')

ezcfg.read_config_file()

# Delete the configuration file. Input permanently delete
ezcfg.delete_config_file()

```
