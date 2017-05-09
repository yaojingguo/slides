## Outline
- Git
- PR Workflow

## Git Basics
- [Git for Computer Scientists]
  (http://eagain.net/articles/git-for-computer-scientists/)

## Git Command
- git init
- git clone
- git commit
- git pull
- git push
- git branch
- git checkout

Demo

## IDE Git Support
Eclipse and IntelliJ IDEA

## PR Workflow
- [Github Pull Request]
  (https://help.github.com/articles/about-pull-requests/)
- [Gitlab Merge Request]
  (https://docs.gitlab.com/ce/user/project/merge_requests/index.html)

Demo

Fixes

Commit message sample:

```
commit 254df01105eb2887729bac90a8d7e7ac5f73f6a0
Author: Peter Mattis <petermattis@gmail.com>
Date:   Mon May 1 14:32:38 2017 -0400

    storage: check whether a replica is destroyed before proposing

    Fix a race where a proposal could be submitted after a replica was
    destroyed. We need to check Replica.mu.destroyed and propose while
    holding Replica.mu.lock.

    Fixes #15551

```

```
commit 637bed5c69fd9aac41bfed0add1e5c008773c47e
Author: Nikhil Benesch <nikhil.benesch@gmail.com>
Date:   Thu May 4 11:21:49 2017 -0400

    build: switch release-upload on whether a tag is present

    Release builds currently operate in two modes: the bleeding-edge mode
    where the latest binary on master is built, and the actual release mode
    where binaries for a tagged SHA are built. To allow for multiple release
    branches, check for the presence of a tag instead of hardcoding that
    "master" means bleeding-edge mode. Now, the presence of a tag means
    actual release mode, and the lack of a tag means bleeding-edge mode.

    Additionally upload non-master bleeding-edge binaries to a subfolder of
    the "cockroach" bucket.

    Since these scripts build and upload bleeding-edge binaries, not just
    release binaries, also update their names to "publish-artifacts" to
    better reflect their purpose.
```
