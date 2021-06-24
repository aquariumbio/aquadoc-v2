# aquadoc-v2

A tool for generating documentation for Aquarium workflows

Note: We are in the process of moving this gem into Aquarium.

# Aquadoc

`aquadoc` will generate a github repository and web page to publish and share a set of [Aquarium](http://klavinslab.org/aquarium) operation types and their protocols.
The generated web page that can be displayed using github pages.

## Installation


## Usage: Command Line

Create a `config.json`.

Your directory structure should look like the following:
    MyWorkflow
    |
    + config.json
    + categories
      |
      + MyCategory1.json
      + MyCategory2.json
      + ...

The README.md file will be used as the front page of the resulting web page.

The config.json file should look something like

```json
{
  "title": "My Workflow",
  "description": "A workflow for doing x, y and z",
  "copyright": "2018 Me or My Organization",
  "version": "0.0.1",
  "authors": [
    { "name": "First Last", "affiliation": "Organization Name" }
  ],
  "maintainer": {
    "name": "First Last",
    "email": "me@my.org"
  },
  "acknowledgements": [
    { "name": "First Last", "affiliation": "Organization Name" }
  ],
  "github": {
    "repo": "name",
    "user": "login",
    "access_token": "40 characters from github"
  }
}
```

Then run

    aquadoc

from within the MyWorkflow directory. This will produce the directory

    MyWorkflow/html

which you can serve up using your favorite web server.

Typically, the entire MyWorkflow directory would be turned into a github repository and github pages would be pointed to the html directory.
You would use github versions, tags, and releases to maintain versions of your code.

## Usage: API

Given a list of categories and a configuration file, you can do

```ruby
require 'aquadoc'

Aquadoc::Git()config, categories).run
```

to generate the github repo.
See the [Aquarium](http://klavinslab.org/aquarium) documentation for more information.

