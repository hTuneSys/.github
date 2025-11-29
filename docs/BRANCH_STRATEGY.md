<!--
SPDX-FileCopyrightText: 2025 hexaTune LLC
SPDX-License-Identifier: MIT
-->

# 📚 Branching Strategy for hTuneSys

This project follows a structured, scalable branching model inspired by GitHub Flow, Gitflow, and real-world enterprise project practices.  
All contributors are expected to adhere to these rules for consistent development and stable releases.

---

## 🔱 Branch Layers and Types

| Branch             | Purpose                                               | Allowed Types (Prefix)                           |
|--------------------|-----------------------------------------------------|-------------------------------------------------|
| `main`             | Production branch. All official releases are tagged here. | N/A (protected branch)                         |
| `release/x.y`      | Pre-release stabilization, final QA and testing.    | N/A (protected branch)                                      |
| `develop`          | Integration branch for ongoing feature and fix PRs. | N/A (protected branch)                          |
| `feature/xyz`      | Development of new features.                         | `feat/`                                        |
| `fix/bug-id`       | Bug fixes and patches.                               | `fix/`                                         |
| `chore/*`          | Routine tasks, maintenance, housekeeping.           | `chore/`                                       |
| `refactor/*`       | Code refactoring without feature or bug changes.    | `refactor/`                                    |
| `test/*`           | Test additions and modifications.                    | `test/`                                        |
| `docs/*`           | Documentation improvements and additions.            | `docs/`                                        |
| `ci/*`             | Continuous Integration and automation scripts.       | `ci/`                                          |
| `perf/*`           | Performance improvements.                            | `perf/`                                        |
| `build/*`          | Build-related changes (packaging, dependencies).     | `build/`                                       |
| `hotfix/*`         | Emergency fixes applied directly on `main`.          | `hotfix/`                                      |
| `style/*`          | Code style and formatting changes.                   | `style/`                                       |

---

## 🔄 Pull Request Flow

### 🔁 For Contributors

- All PRs **must be based on `develop`** unless hotfixing `main`.
- Branch names should start with one of the allowed prefixes from the table above.
- PR titles must follow [Conventional Commits](https://www.conventionalcommits.org/) format.
- Keep your PR focused and small for easier review.

### ✅ Merge Rules

- `feature/*`, `fix/*`, `chore/*`, `refactor/*`, `test/*`, `docs/*`, `ci/*`, `perf/*`, `build/*`, `style/*` → merge into `develop` after review & CI pass.
- `develop` → `release/x.y` at sprint end for release prep.
- `release/x.y` → `main` after QA and approval.
- `hotfix/*` → `main` → `develop` immediately.

---

## 🔐 Branch Protection Rules

| Branch       | Protection                              |
|--------------|----------------------------------------|
| `main`       | Required PR, review, status checks      |
| `release/*`  | Only maintainers can merge              |
| `develop`    | PR required, minimum 1 review           |
| others       | No restriction, delete after merge      |

---

## 🗓️ Merge Schedule

| Action                      | Frequency            |
|-----------------------------|----------------------|
| `feature/*` → `develop`     | As soon as ready     |
| `develop` → `release/x.y`   | Weekly or per sprint |
| `release/x.y` → `main`      | After QA/approval    |
| `hotfix/*` → `main`         | Immediately if needed|

---

## 🧹 Cleanup Policy

- Merged feature, fix, chore, refactor, test, docs, ci, perf, build, style branches **must be deleted immediately**.
- `release/*` branches are deleted **after tagging**.
- `hotfix/*` branches are merged and deleted **immediately**.
- Consider automating branch deletion using GitHub Settings or scripts.

---

## 📈 Do’s and Don’ts

### Do

- Use **clear, descriptive branch names** with allowed prefixes.
- Open **small, focused PRs** for faster review.
- Follow **commit and PR title conventions**.
- Sync with `develop` frequently.

### Don’t

- Push large or unrelated changes in a single PR.
- Merge into `main` or `release/*` without approval.
- Use branch names outside the approved prefixes.
- Forget to delete branches after merge.

---

## 🔄 PR Flow Diagram (Textual)

```text
feature/*, fix/*, chore/* ... -> develop -> release/x.y -> main
                                ↑               ↑
                           hotfix/* ------------|
```

---

## 📬 Questions?

If you have questions or need help, open a discussion at:  
[https://github.com/hTuneSys/hTuneSys/discussions](https://github.com/hTuneSys/hTuneSys/discussions)

---

> Maintained by @husamettinarabaci · hexaTune LLC
