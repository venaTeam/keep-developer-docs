# Contributing

Thanks for helping improve the Keep developer documentation. The full conventions live in [`contributing.mdx`](./contributing.mdx) (rendered as part of the doc site). This file is the GitHub-rendered short version.

## Local preview

```bash
npm install
npm run dev
```

The site runs at `http://localhost:3000`. Mintlify hot-reloads `.mdx` edits.

## Adding a page

1. Create the `.mdx` file under the correct folder (`architecture/`, `services/`, `components/`, `operations/`).
2. Add the file path (without the `.mdx` extension) to the relevant `pages` array in `mint.json`.
3. Open a PR — preview deployments are produced automatically.

## Conventions

- Keep prose tight. A developer should be able to skim a page and find the answer within 30 seconds.
- Quote actual file paths and function signatures from the service repos. Do not paraphrase code if you can copy it.
- Document **what is** before **what should be**. If a feature is not implemented yet, mark it explicitly with "tracked" or "roadmap".
- Update `mint.json` in the same PR as any rename / move.

## Commit messages

We use the Angular commit-parser convention (same as the other Keep repos):

```
feat(architecture): document Kafka envelope
fix(services): correct event-handler port
docs: update getting-started with new repo URL
```

Allowed tags: `build, chore, ci, docs, feat, fix, perf, style, refactor, test`.

## Where to ask questions

- Architectural questions → open a discussion in the relevant service repo.
- Doc-tooling questions → open an issue here.
