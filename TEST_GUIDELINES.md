# Fix the Broken Repository

**Estimated time:** 20 - 30 minutes
**What we evaluate:** Git fundamentals, problem-solving, commit hygiene, and explanation quality

## Overview

You are given a Git repository with several intentional issues that need to be fixed. This exercise tests your ability to:
- Navigate and understand Git history
- Clean up messy commits
- Fix mistakes safely
- Resolve conflicts
- Handle security issues
- Work with branches effectively

## Setup

1. Navigate to the broken repository directory: `broken-repo-13924`

2. Review the repository structure and commit history

## Repository Setup

The repository contains:
- Simple text files (notes.txt, todo.txt, README.md, etc.)
- Multiple branches with intentional issues
- A commit history with various problems

**Important:** You may use any Git commands, but do NOT delete the repository history. All fixes should preserve the existing commit structure where possible.

## Tasks

### Task 1: Inspect the History

Review the commit history and identify the following issues:

1. One commit that mixes unrelated changes
2. One commit that introduced incorrect content
3. One commit that contains sensitive information (API key or secret)

**Deliverable:**
Briefly describe what you found and which commits are problematic. You can document this in a file called `TASK1_FINDINGS.md` or include it in your final README.

**Commands to get started:**
```bash
git log --oneline --all --graph
git log --stat
git show <commit-hash>
```

### Task 2: Clean Up Commit History

A commit titled "quick fix" contains multiple unrelated changes.

**Requirements:**
- Split it into at least 3 logical commits
- Use clear, conventional commit messages (e.g., `feat:`, `fix:`, `refactor:`)
- Preserve authorship
- The final history should be clean and readable for a pull request

**Hint:** Use interactive rebase to split the commit.

### Task 3: Fix the Mistake Safely

A recent commit introduced incorrect content in a file.

**Requirements:**
- Undo the incorrect change without rewriting public history
- The fix should be visible as a new commit
- Explain why you chose your approach (revert vs reset vs other)

**To verify:** Check the content of todo.txt - it should be correct after your fix.

### Task 4: Resolve a Merge Conflict

You will encounter a conflict between `main` and `feature/login` branches.

**Requirements:**
- Merge `feature/login` into `main` (or rebase it onto `main`)
- Resolve the conflict correctly
- Ensure all content is preserved correctly
- Commit the resolution with a clear message

**Hint:** The conflict is in `notes.txt`. Both branches made valid changes that need to be combined.

### Task 5: Remove Leaked Secrets

A commit includes an API key hardcoded in a file.

**Requirements:**
- Remove the secret from the current working tree
- Document what you would do in a real production scenario
- Do NOT commit a new secret or hardcode another key
- Explain the steps you would take if this happened in production

**Note:** For this exercise, you don't need to rewrite history to remove the secret from past commits (that would require `git filter-repo` or similar). Just remove it from the current state and explain your production approach.

### Task 6: Rebase and Sync

Your `feature/login` branch is behind `main`.

**Requirements:**
- Rebase `feature/login` onto the latest `main`
- Resolve any conflicts that arise
- Ensure your branch is up to date
- Explain why you chose rebase vs merge

### Task 7: Recover Lost Commit (Bonus)

A commit was accidentally deleted (reset) on the `feature/login` branch. Your task is to recover it.

**Requirements:**
- Use Git's reflog to find the lost commit
- Recover the commit to a new branch or cherry-pick it
- Explain the process you used to find and recover it
- Document what the lost commit contained

**Hint:** Use `git reflog` to view the reference log and find commits that are no longer in the current branch history.

**Note:** This is a bonus task that demonstrates your ability to recover "lost" work, which is a valuable skill in real-world scenarios.

## Final Deliverables

1. **A link to your Git repository** - Please push your completed repository to GitHub, GitLab, or Bitbucket and provide the repository link. This is the preferred submission method. Alternatively, you may submit a zip file of your repository.

2. **A README.md file** in the repository root explaining:
   - What commands you used (high-level overview, not every keystroke)
   - Why you chose rebase vs merge (for Task 6)
   - How you identified and fixed each issue
   - How you would avoid these issues on a team
   - Any challenges you encountered

3. **Your fixed repository** with:
   - Clean commit history
   - All files correct
   - No secrets in the codebase
   - All conflicts resolved
   - Branches properly synced

## Evaluation Criteria

We are **not** looking for perfection. We care about:

- ✅ **Safe Git usage** - Using appropriate commands for the situation
- ✅ **Clean, logical commits** - Meaningful commit messages and logical groupings
- ✅ **Ability to recover from mistakes** - Knowing how to find and fix issues
- ✅ **Clear explanations** - Understanding why you made certain choices
- ✅ **Respect for shared history** - Not force-pushing or rewriting public history inappropriately

**Bonus points for:**
- Interactive rebase usage
- Meaningful commit messages following conventions
- Calm, methodical workflow
- Understanding when to use revert vs reset vs rebase

## Getting Help

You may use:
- Git documentation (`git help <command>`)
- Online resources
- Your IDE's Git tools

However, the exercise should be completed independently - no asking others for solutions.

## Time Management

If you're running short on time, prioritize:
1. Task 1 (Inspection) - Quick but important
2. Task 3 (Fix the mistake) - Core functionality
3. Task 4 (Merge conflict) - Common real-world scenario
4. Task 2 (Clean history) - Can be simplified if needed
5. Task 5 (Secrets) - Document approach even if incomplete
6. Task 6 (Rebase) - Important but can be simplified
7. Task 7 (Lost commit) - Bonus task, demonstrates advanced recovery skills

## Submission

Once complete, provide:
- **Your Git repository link** - Push your repository to GitHub, GitLab, or Bitbucket and share the link. This is the preferred submission method.
- Your README.md with explanations
- Any additional notes or findings

**Note:** If you cannot push to a Git hosting service, you may submit a zip file of your repository instead.

Good luck
