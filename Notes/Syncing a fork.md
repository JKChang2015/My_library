### Syncing a fork
---
1. Open Terminal
2. Change the current working directory to your local project.

3. check all the remote status:<br/>
   `$ git remote -v`<br/>

4. if not exsiting, add a upstream<br/>
   `$ git remote add upstream <upstream url>`<br/>

5. Fetch the branches and their respective commits from the upstream repository. Commits to `master` will be stored in a local branch, `upstream/master`. <br/>
`$ git fetch upstream`<br/>

6. Check out your fork's local `master` branch.<br/>
`$ git checkout master`<br/>

7. Merge the changes from `upstream/master` into your `local` master branch. This brings your fork's `master` branch into sync with the upstream repository, without losing your local changes.<br/>
`$ git merge upstream/master`


