# Goal: want to create a separate repository for a folder in an existing project

Source of [help](https://github.com/blog/2104-working-with-submodules) 

Example:

Existing project: programming-problems

Folder that needs a standalone repository programming-problems/src/util/histogramprinter

Outside project root directory programming-problems

`cp -r programming-problems/src/util/histogramprinter histogram-printer`

`cd histogram-printer`

check and copy path

`pwd` 

`git filter-branch --subdirectory-filter <path above> -- --all`

Create a new repository for histogram-printer on Github

repo url: https://github.com/shane030716/histogram-printer

still in histogram-printer

`git remote set-url https://github.com/shane030716/histogram-printer`

go back to programming-problems

delete original folder

`git rm -r src/util/histogramprinter histogram-printer`

commit

`git commit -m "Remove subfolder (preparing for submodule)"`

add submodule, but it should be empty inside

`git submodule add https://github.com/shane030716/histogram-printer histogramprinter`

commit

`git commit -m "histogramprinter (histogram-printer) submodule"`

### Pull updates from submodule
[This](http://stackoverflow.com/questions/5828324/update-git-submodule-to-latest-commit-on-origin) says `git submodule update` command actually tells Git that you want your submodules to each check out the commit already specified in the index of the superproject.
So probably don't need this `git submodule update --init --recursive`

If you want to update your submodules to the latest commit available from their remote, you will need to do this directly in the submodules.

Inside submodule folder, checkout or/and pull

`git checkout master`

`git pull origin master`

go back to programming-problems root

`git commit -am 'Pulled Down update to submodule'

`git push`

Or

`git submodule foreach git pull origin master`

`git commit -am 'Pulled Down update to submodule`

`git push`


### Now making changes directly in the submodule

Inside submodule after making change

for the first time
`git checkout master`

`git commit -a -m 'commit directly in submodule'`

`git push`

Go back to project root

And use the steps in Pull updates from submodule