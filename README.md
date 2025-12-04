# Jujutsu Cheat sheet

This is a quick reference guide for using Jujutsu, a distributed version control system.
And is not a substitute for the full documentation.
Documentation can be found at: [Jujutsu Documentation](https://docs.jj-vcs.dev/latest/).


### Initial Configuration

### Setting up your identity globally

```bash
jj config set --user user.name "Anonymous"
jj config set --user user.email "anon@local"
```

### Setting up your identity for a specific repository

``` bash
# applies configuration to a single repository only
#             vvvvvv
jj config set --repo user.name "Alice"
jj config set --repo user.email "alice@local"

# reset already recorded global authorship information:
jj metaedit --update-author

```

### Common Commands
#### Basic commands
```bash
jj new  #Creates a new, empty commit on top of the current one.
jj new <change-id> #Creates a new commit based on a specific revision.
jj log  #Shows recent commits.
jj describe #Sets or changes the commit message (description) for the current or a specified commit.
jj diff #Compares the content of files between two revisions.
jj edit <change-id>  #Switches the working copy to a specific change.
jj status #Shows the current state of the working copy, including uncommitted changes.
jj commit #Saves the current changes in the working copy as a new commit.
```
#### History and rewriting
```bash
jj split #Splits a commit into two.
jj squash #Combines changes from two commits into one.
jj abandon #Removes changes from your local history.
jj interdiff --from @-- --to @ #Compares changes between two commits, useful for pull request iterations.
```
#### Git compatibility
```bash
jj git init --colocate #Initializes a new, colocated jj repository alongside a Git repository.
jj git fetch #Fetches updates from a remote, which updates local bookmarks for remote branches.
jj git push #Pushes the current change to a remote.
```
#### Other useful commands
```bash
jj bookmark #Manages bookmarks, which function like branches.
jj config #Manages configuration options.
jj run #Executes scripts, such as build systems, linters, or formatters.
jj diffedit #Lets you edit the content changes in a revision with a diff editor.
```

#### Creating a new repository

```bash
jj init my-repo # Creates a new jj repository in the "my-repo" directory
cd my-repo
```
