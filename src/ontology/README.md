
Deploying a new version of OArCS
================================

These instructions only concern deploying a new version of OArCS.  Necessary steps for preparing new data are covered elsewhere. These instructions assume you have a Github account, have Java installed, are using OSX or linux, and that you have [generated an ssh key and linked it to your Github account][0]. 

Clone the OArCS repository
--------------------------

You only have to do this once. Clone the oarcs github repository. You will have to be a member of the repository to commit changes, ask the owners to be added to the project.

``` 
  git clone git@github.com:aszool/oarcs.git
```


Clone the build repository 
--------------------------

You only have to clone the repository once. Using git in the terminal window:

```
  git clone git@github.com:SpeciesFileGroup/mx_owl_builders.git 
```

Build a new instance of the ontology
------------------------------------

In the terminal cd into mx_owl_builders/ 

```
   cd mx_owl_builders
```

Run the build script. This assumes you are connected to the internet.

```
  ./build_oarcs.sh
```

You should see a number of owl files in the directory.
 

Update the OArCS repository
---------------------------

Copy (and replace) the ```oarcs.owl``` file generated from build_oarcs.sh command to the OArCS repository, it lives at:

```
  oarcs/src/ontology/oarcs.owl
```

Commit and push the changes using git. This assumes you are in a terminal insided the oarcs/ directory.

```
  git add src/ontology/oarcs.owl
  git commit -m 'Include short but detailed message here as to what changed.'
  git push
```

[0]: https://help.github.com/articles/generating-ssh-keys/
