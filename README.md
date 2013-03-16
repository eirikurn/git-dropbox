Archive git repositories to your dropbox folder.

## INSTALLATION

You can install it with `npm`.

```
npm install -g git-dropbox
```

## BASIC USAGE

From anywhere:

```
git dropbox https://github.com/eirikurn/my-repo.git
```

This will clone the repo as a bare repo at `~/Dropbox/git/my-repo.git`.

When runnin `git dropbox` inside a repo with no arguments, the `origin` remote
will be cloned to your dropbox folder. It will also add the new repo as a 
`dropbox` remote.

```
git dropbox
git push dropbox master
```

When you have repos in your dropbox they can then be cloned on any of your computers by running.

```
git clone ~/Dropbox/git/my-repo.git
```

Be careful not to push to the dropbox repo from two computers at the same time,
it will cause a dropbox conflict and corrupt the repo.

## OVERRIDE TARGET

You can override where it is cloned with the `GIT_ARCHIVE_FOLDER` env
variable:

```
export GIT_ARCHIVE_FOLDER=~/Dropbox/git/archive
git dropbox <repo>
```