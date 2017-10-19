# Debian Git Repositories Image

Based on [kemixkoo/debian-maven](https://hub.docker.com/r/kemixkoo/debian-maven/)


# Usage
```
docker run --rm -v /path/to/sources:/workspace/sources \
    -v /path/to/.ssh:/root/.ssh \
    kemixkoo/debian-git-repos
```
Will do "git status" for all sources git repositories., and show status logs in console.

# Deamon Run
```
docker run -d -v /path/to/sources:/workspace/sources \
    -v /path/to/.ssh:/root/.ssh \
    -it kemixkoo/debian-git-repos /bin/bash
```

When in deamon mode with -d option, need add  -i (--interactive) with "/bin/bash".
Else, the container can't be deamon mode.

Then, in Jenkins or consle, can use docker exec command to do any commands, eg:
```
docker exec <running_constainer_id> ./gitx.sh pull --rebase -p
```


# Building
```
docker build -t kemixkoo/debian-git-repos .
```
