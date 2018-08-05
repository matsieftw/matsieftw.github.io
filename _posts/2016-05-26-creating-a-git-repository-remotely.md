---
layout: post
title: Creating a Git Repository Remotely
---

I have been banging my head on my keyboard for quite some time trying to figure out why using `git push origin master` has never seemed to work for me when trying to push the few local repos I have to github via the command line. I knew I was missing something essential about the process, but was struggling to put my finger on it.

Finally, I've found out there is no established git command that creates the repo when you attempt to push a local repo up. **The repo has to have already been created.** This posed a bit of an issue for me because I try to do as much of my work as possible via the command line.

Turns out, `curl` is perfect for just such a situation.

`curl -u 'USERNAME' https://api.github.com/user/repos -d '{"name":"REPO_NAME"}'`

This command will create a new repo in your profile using the github API.