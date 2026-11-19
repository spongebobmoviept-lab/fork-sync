# fork-sync

Keeps Mike's GitHub forks up to date with the projects they were forked from.

- Every hour (at :15) a GitHub Action copies the main branch and
  every tag from the original project into Mike's fork. Run it any time from the
  Actions tab. (Not every branch: upstream rebases its PR/bot branches constantly.)
- Forks synced now: `morluto/rea` -> `spongebobmoviept-lab/rea`.
- It never force-pushes. If the original rewrites history or the fork has its own
  commits, the run fails and GitHub emails Mike; nothing is overwritten.
- Each fork has its own write deploy key; the private half is a secret in this repo.
- To add a fork: new deploy key on it, new secret here, copy the job in
  `.github/workflows/sync.yml`.
