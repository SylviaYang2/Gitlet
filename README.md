# Gitlet - our own version of Git
- Implemented a version-control system using Java that mimics commit, branch, merge, remote push/pull, and other main features of Git.
- Utilized LinkedHashMap to store and match commit id and blobs, and to construct the commit tree. Serialized and deserialized the runtime objects using the SHA-1 cryptographic hash function. Tested functionalities with unit and integration tests.

# Commands:
- init: Creates a new Gitlet version-control system in the current directory.
- add: Adds a copy of the file as it currently exists to the staging area.
- commit: Saves a snapshot of tracked files in the current commit and staging area so they can be restored at a later time, creating a new commit. 
- rm: Unstage the file if it is currently staged for addition. If the file is tracked in the current commit, stage it for removal and remove the file from the working directory if the user has not already done so (do not remove it unless it is tracked in the current commit).
- log: Starting at the current head commit, display information about each commit backwards along the commit tree until the initial commit, following the first parent commit links, ignoring any second parents found in merge commits.
- global-log: Like log, except displays information about all commits ever made. 
- find: Prints out the ids of all commits that have the given commit message, one per line. 
- status: Displays what branches currently exist, and marks the current branch with a *. 
- checkout: Checkout is a kind of general command that can do a few different things depending on what its arguments are. 
1. java gitlet.Main checkout -- [file name]
2. java gitlet.Main checkout [commit id] -- [file name]
3. java gitlet.Main checkout [branch name]
- branch: Creates a new branch with the given name, and points it at the current head node.
- rm-branch: Deletes the branch with the given name. This only means to delete the pointer associated with the branch; it does not mean to delete all commits that were created under the branch, or anything like that.
- reset: Checks out all the files tracked by the given commit. Removes tracked files that are not present in that commit. Also moves the current branch's head to that commit node.
- merge: Merges files from the given branch into the current branch.
- add-remote: Saves the given login information under the given remote name. Attempts to push or pull from the given remote name will then attempt to use this .gitlet directory. 
- rm-remote: Remove information associated with the given remote name. 
- push: Attempts to append the current branch's commits to the end of the given branch at the given remote. 
- fetch: Brings down commits from the remote Gitlet repository into the local Gitlet repository.
- pull: Fetches branch [remote name]/[remote branch name] as for the fetch command, and then merges that fetch into the current branch.
