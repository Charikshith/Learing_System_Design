Here’s a **simple, beginner-friendly blog post** you can use or publish directly.

---

# Understanding Code Versioning: From Version 1 to Version 2 (and Back Again)

When you work on software, your code changes constantly. You fix bugs, add features, and improve performance. But what happens when a new change breaks your application in production?

This is where **code versioning** becomes essential.

In this post, we’ll walk through:

* What code versioning is
* Why it matters
* How to version your code from **v1** to **v2**
* How versioning helps with rollbacks

No advanced knowledge required.

---

## What Is Code Versioning?

Code versioning means **keeping track of every meaningful change in your code**, so you can:

* Go back to an older version if something breaks
* See what changed and when
* Collaborate safely with others

Instead of saving multiple folders like:

```
project_v1/
project_v2/
project_final/
```

Professional software teams use **Git**, a version control system.

---

## Where Are Code Versions Stored?

There are two main places:

1. **Locally**, inside your project (handled by Git)
2. **Remotely**, on platforms like GitHub, GitLab, or Bitbucket

The remote repository is important because it acts as:

* A backup
* A shared source of truth
* A rollback point for production

---

## Version 1: Saving Your First Stable Code

Let’s say you’ve written your first working version of your application.

You save it like this:

```bash
git init
git add .
git commit -m "Initial version"
```

Now you label this version as **v1.0.0**:

```bash
git tag v1.0.0
git push origin v1.0.0
```

This tag marks a **stable release**.
You can always come back to it.

---

## Version 2: Adding New Features

Next, you add two new features.

After completing the work:

```bash
git add .
git commit -m "Add feature A and feature B"
```

Then you create a new version:

```bash
git tag v2.0.0
git push origin v2.0.0
```

Now your project has:

* **v1.0.0** → original stable version
* **v2.0.0** → new features

---

## How Version Numbers Work (Simple Explanation)

Most teams follow **Semantic Versioning**, which looks like this:

```
MAJOR.MINOR.PATCH
```

* **MAJOR** → breaking changes
* **MINOR** → new features
* **PATCH** → bug fixes

Examples:

* `v1.0.0` → first release
* `v1.1.0` → added a feature
* `v1.1.1` → fixed a bug
* `v2.0.0` → major change that breaks compatibility

---

## Why Versioning Is So Important

Imagine you deploy version 2 and discover a serious bug in production.

Without versioning:

* You panic
* You try to “fix it quickly”
* You risk making things worse

With versioning:

* You simply roll back to **v1.0.0**
* Users are safe
* You debug calmly

This is why versioning is a **production safety net**.

---

## A Simple Rule to Remember

> **Commits track changes**
> **Tags define versions**
> **Remote repositories keep your code safe**
> **Deployments should always use tagged versions**

---

## Final Thoughts

Code versioning isn’t just for large companies or big teams.
Even if you’re working alone, it:

* Saves time
* Prevents disasters
* Makes your work more professional

If you can version your code properly, you’re already thinking like a production engineer.

---

If you want, I can also help you write:

* A follow-up post on **rollbacks**
* A guide on **versioning databases**
* A beginner-friendly post on **Git branching**

Just tell me what’s next 🙂
