---
title: Managing multiple git profiles
---

i need version control for my personal projects as well as my work projects. my work github is separate, but sometimes i’ll want to develop both on the same device. this requires two accounts, two tokens, two profiles, etc.

### setup steps (informed by chatgpt and various online resources):

1. generate 2 ssh keys
2. add them to ssh config
3. configure them with an alias, and remember these
4. add each public key to the respective github account

this will properly configure both profiles and enable you to use them later.

### usage

we can now set them per repo using `git config`. for example:

```bash
cd personal_repo
git config user.name "siyang"
git config user.email "siyang@email.me"
```

we can then check using

```bash
git config user.name
git config user.email
```

this will change whose name gets stamped on the commit. however, it’s still gonna fail authentication if we’re on https (can confirm this with `git remote -v`)

if we set the ssh config properly before, we can just update the remote with this new alias

```bash
git remote set-url origin git@github-personal:siyang/personal_repo.git
```

and then confirm using `ssh -T git@github-personal`

### other useful tidbits

if you’re like me, you might have already accidentally committed with the wrong profile. this is how to undo that:

```plaintext
git reset --soft HEAD~1
```