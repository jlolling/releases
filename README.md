# Talend Open Studio Branches and Releases

> How works Talend Open Studio release system?
>
> What is the difference between the release 2.0.1 and milestone 2.1.0M2?

A release is a kind of snapshot at a precise instant.
Release 2.0.2 will never be modified.
If needed, a release 2.0.3 will appear.
The snapshot is taken on a branch, release 2.0.2 is a snapshot taken on branch 2.0.

A branch evolves: improvement and bug fixing.
But a branch does not move considering its features: there should be no additionnal
features in release 2.0.3 than in release 2.0.2, only code improvement, bug fixing and so on.

## Data

See [talend_open_studio_releases.csv](talend_open_studio_releases.csv) for a machine-readable format.

Format is CSV, `,`-separated fields as in order:

* Milestone
* Build id/tag/timestamp
* Release date

Excerpt:

```csv
"Milestone","Build Tag","Release Date"
1.0.0,51,2006-10-03
...
7.3.1M6,20200117_1600,2020-01-22
```

## Graph

TODO,

## Release numbers: x.y.z

* `x`: the major release number, incremented when a big change is introduced.
* `y`: the minor release number, additionnal features
* `z`: the Service Pack number. \
  No new features between 2 Service Pack, *only bug correction*, differences between 2.0.0 and 2.0.1 are really minor but sometimes very important (security fixes for example).

## Parallel working

The main advantage of branch versionning is that
TOS dev team can still create new fixing releases on an old branch
even if a new branch has been available since.

For example, if you find some bugs in release 2.0.2,
TOS dev team will certainly fix bugs for a release 2.0.3
even if release 2.1.0 has already been out for a while.


## Milestones, Release Candidate, Main

When preparing a release, it has to be tested and qualified.
TOS dev team works as follows :

* milestones `x.y.zM#` are snapshot from master, the development main branch. \
  Milestones are designed for test by most impatient and advanced users. \
  It is obvious for the dev team that this release may contain bugs
  even if we work to make them as few as possible. \
  The purpose is to list them all to prepare the release candidates...
* release `x.y.zRC#` is also a snapshot from master. \
  The purpose is to fix all blocking bugs before releasing the main release.
* release `x.y.z` is a main release.

Example: 2.0.0M1 >> 2.0.0M2 >> 2.0.0M3 >> 2.0.0M4 >>2.0.0RC1 >> 2.0.0 >> 2.0.1


---
