---
layout: post
title: "Updating tor leads to keys, and ansible, and editors"
date: 2018-10-18
---

Good Timezone!

Today I decided to dig into why my tor relays wouldn't update. I mean, what else is there to do at 4 am when on vacation?

Good news. If I had a cron set up to renew the keys, I wouldn't have run into issues. Better news, because I didn't, I got to learn a bunch of new things regarding sysadmin.

First, How to update a repo's apt signing keys. (much thanks to [https://linux-audit.com/how-to-solve-an-expired-key-keyexpired-with-apt/](https://linux-audit.com/how-to-solve-an-expired-key-keyexpired-with-apt/))

Second, Ansible can do things locally. ([https://docs.ansible.com/ansible/latest/user_guide/playbooks_delegation.html](https://docs.ansible.com/ansible/latest/user_guide/playbooks_delegation.html)) Which is interesting to discover when you discover it's looking for things on your local box, and not on the remote box where the commands run great manually.

Finally, `git var` ([https://git-scm.com/docs/git-var](https://git-scm.com/docs/git-var)) This is a really nice command when you can't figure out why your commit editor is nano instead of vim and none of the envs mentioned in the man page for <code>git-config</code> seem to be set.
