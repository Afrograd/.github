# Contributing to AfroGrad

Welcome, and thank you for working with us. This guide applies to every
repository in the AfroGrad organization unless a repository has its own
`CONTRIBUTING.md`.

Read it once before your first pull request. Your reviewer will point back to
it when something is off.

---

## 1. Before you start

1. **Read the repository's own docs first.** In `Afrograd-Connect` that means
   `AGENT_PROTOCOL.md`, `PRD.md`, `roadmap.md` and, for any UI work,
   `DESIGN_SYSTEM.md`.
2. **Work from an issue.** Every change should have an issue that says what
   and why. If there isn't one, open one (use the templates) and wait for a
   maintainer to confirm the scope before you write code.
3. **Stay inside the current roadmap phase.** Work outside it needs sign-off
   from a maintainer first.
4. **Ask early.** If you are stuck for more than an hour, comment on the issue
   or open a draft pull request and ask. Nobody expects you to know the
   codebase yet.

## 2. Branches

- Never push to `main`. All work goes through a pull request.
- One branch per issue, created from the latest `main`.
- Name it `<type>/<issue-number>-<short-description>`, for example
  `feat/42-quiz-timer` or `fix/57-login-redirect`.

Types: `feat`, `fix`, `docs`, `test`, `refactor`, `chore`, `content`.

## 3. Commits

- Small commits that each do one thing.
- Message format: `<type>(<area>): <what changed>`, in the imperative mood.
  - Good: `fix(quiz): keep the selected answer after a re-render`
  - Bad: `fixed stuff`, `wip`, `update App.tsx`
- Explain *why* in the commit body when it is not obvious.
- Never commit secrets, API keys, `.env` files or generated build output.

## 4. Before you open a pull request

Run the checks yourself. CI runs the same ones, and a red pull request is not
reviewed.

For `Afrograd-Connect`:

```bash
npx tsc --noEmit        # types
npm test                # frontend tests
npm run build           # production build
npm run check:bundle    # bundle size budget
pytest backend/tests    # only if you touched backend/
```

Also:

- If you changed behaviour, add or update a test.
- If you touched UI, check it in **light and dark mode** and at **phone
  width (390px)**. Use semantic colour tokens, never hard-coded hex values.
- If you added a database table, add its row-level security policy in the
  same pull request. Do not apply migrations yourself.

## 5. Pull requests

- **Keep it small.** Aim for under 400 changed lines. Large features are split
  into several pull requests.
- **Fill in the pull request template.** Link the issue with `Closes #123`.
- **Show your work.** Say exactly what you tested and how. Add screenshots or
  a short recording for anything visual.
- **Open it as a draft** if it is not ready, and mark it ready for review when
  it is.
- **Keep it up to date** with `main`. Resolve merge conflicts on your branch.

## 6. Review and merging

Every pull request is reviewed before it is merged:

1. **Automated review.** An AI reviewer checks CI, reads the change, and
   leaves comments: bugs, missing tests, security problems, and anything that
   breaks these guidelines.
2. **You respond.** Fix what is asked and push to the same branch, or reply
   explaining why not. Do not close the pull request and open a new one.
   Resolve a comment thread only once it is addressed.
3. **Maintainer approval.** When the pull request is green and the review is
   clean, a maintainer is asked to approve it. **Only a maintainer-approved
   pull request is merged.**
4. **Squash merge.** Pull requests are squash-merged into `main`, so the pull
   request title becomes the commit message. Write it well.

Review comments are about the code, not about you. Everyone's code gets
comments, including the maintainers'.

## 7. Never

- Push to `main`, force-push to someone else's branch, or merge your own pull
  request.
- Skip, delete or disable a test to make CI pass.
- Put API keys or provider credentials in frontend code.
- Apply database migrations to a shared environment.
- Copy code you do not understand into the codebase. If you used an AI
  assistant, you are still responsible for every line.

## 8. Getting help

Comment on your issue or pull request, or email **afrogradone@gmail.com**.
