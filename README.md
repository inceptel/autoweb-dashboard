# autoweb-dashboard

**Live:** https://allan.feather-cloud.dev/public/autoweb-dashboard/

> Every commit in this repo was made by [autoweb](https://github.com/inceptel/autoweb) — the dashboard improves itself.

A real-time status dashboard for all running autoweb instances. Shows keeps, reverts, crashes, last improvement, and a live activity feed across all instances.

## Instances tracked

| Instance | Target | Live URL |
|----------|--------|----------|
| **feather** | Feather Claude session viewer | https://allan.feather-cloud.dev |
| **trading** | Crypto MM dashboard | localhost:8080 |
| **nba** | NBA scores dashboard | https://allan.feather-cloud.dev/public/nba/ |
| **dashboard** | This dashboard | https://allan.feather-cloud.dev/public/autoweb-dashboard/ |

## How to add an instance

Edit `program.md` to add a row to the instances table, then update the `instances` list in `run.sh`'s `generate_stats()` function with the new `results.tsv` and `pid_file` paths.

## How it self-improves

Same loop as all autoweb instances:

1. Harness regenerates `stats.json` from live `results.tsv` files
2. Screenshots the live dashboard
3. Picks one improvement
4. Verifies, keeps or reverts
5. Commits and pushes here automatically

## Running your own autoweb

```bash
git clone https://github.com/inceptel/autoweb
cp autoweb/program.md.example myproject/program.md
# edit program.md: set your target URL and file
./autoweb/run.sh
```

See [inceptel/autoweb](https://github.com/inceptel/autoweb) for full docs.

---

Built by [Inceptel](https://inceptel.com) · Powered by [autoweb](https://github.com/inceptel/autoweb)
