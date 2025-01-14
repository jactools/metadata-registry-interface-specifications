# Metadata Registry Interface Specifications

## Introduction

Project Name: Metadata Registry Interface Specifications

Previous working titles: Central Metadata Catalog, Metadata Hub

### Background, motivation, context

The project was introduced in July 2020 to provide initial information to the Analyics team on how they could deliver metadata information for lineage purposes to Informatica Enterprise Data Catalog. The solution should be independent of Informatica EDC however, as in the future Informatica EDC will be replaced by an overall, end-to-end metadata management solution.

Hence, a few interface descriptions were needed and this Git repository stores and maintains them.

>NOTE: We are talking about Design-Time Metadata, not about operational metadata.

In the json schemas you will e.g. find 'physical entity', which might be a file. The file name property will then be technical, but still excluding any operational parts.

#### Example Physical Entity

The actual filename in an interface is customer_info.20200706-095200.txt. 
In the metadata we will expect "customer_info" as technical entity name.

>NOTE: We require operational metadata to deliver the design-time metadata it links to. 


##Table of contents

* This README: installing and testing your installation
* In [USAGE.md](USAGE.md):
  * More about the Metadata Registry interfaces;
  * The configuration explained;
* For more information about the authors, getting in touch and contributing, see [CONTRIBUTING.md](CONTRIBUTING.md);
* See [CHANGELOG.md](CHANGELOG.md) for an overview of versions of the Metadata Registry Interfaces;
* Finally, see [TODO.md](TODO.md) for an overview of known issues (always good to be aware of these), ideas and backlogs, and any other stuff we have on the list.

> NOTE: this is the first iteration of the documentation, explaining the basics of the interfaces. Going forward we will build up a full fledged manual with many more examples and references. Your feedback is valuable!

## Contribute

The python script in this repository verifies sample json files against the json schemas.
Python versions tested: 3.6, 3.8, 3.9

```
# Clone repository
git clone https://github.com/jactools/metadata-registry-interface-specifications
cd metadata-registry-interface-specifications

# Create a virtualenv
python3 -m venv venv
# Linux/MacOS:
source ./venv/bin/activate
# Windows:
venv\Scripts\activate

# Enable proxy (optional)
export https_proxy=<some_proxy>:8080

# Copy the version file to temp, so the number can be increased automatically
mkdir -p temp
cp -p plugins/__init__.py temp/_tmp_version.tmp

# Install package requirements
pip3 install -r requirements.txt
```

## Testing
After following the steps mentioned in Contributing, test the example json files against the schema version. Change validate_example_schemas.py to point to the correct directories and schema version.
Make sure you've activated the virtual environment.

```
cd tests
(venv) me@Home tests % python3 validate_example_schemas.py
```
Output:
```
.......
----------------------------------------------------------------------
Ran 7 tests in 0.006s

OK
```

---
That's it! Read on in [USAGE.md](USAGE.md) to learn more, check [CONTRIBUTING.md](CONTRIBUTING.md) to get in touch and [TODO.md](TODO.md) to see a list of known issues.
