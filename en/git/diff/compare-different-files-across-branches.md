# Compare Different Files Across Branches

To compare the same file across different branches, you can use the following command:

```git
git diff main develop -- path/to/file
```

However, if both the branch and the file are different, use this form instead:

```git
git diff main:path/to/file1 develop:path/to/file2
```

This command also works when comparing the same file between branches,
so it’s a flexible approach worth remembering.

A common use case is when a repository is structured with separate directories for each environment.
For example, you can use this to compare development and production configuration files across the main and develop branches.

You can also replace branch names with tags:

```git
git diff v1.0.0:path/to/file1 v2.0.0:path/to/file2
```
