### Syncing a fork
---
1. Open Terminal
2. Change the current working directory to your local project.
3. Fetch the branches and their respective commits from the upstream repository. Commits to `master` will be stored in a local branch, `upstream/master`. <br/>
`$ git fetch upstream`<br/><br/>
4. Check out your fork's local `master` branch.<br/>
`$ git checkout master`<br/><br/>

5. Merge the changes from `upstream/master` into your `local` master branch. This brings your fork's `master` branch into sync with the upstream repository, without losing your local changes.<br/>
`$ git merge upstream/master`