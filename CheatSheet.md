# Git CheatSheet

## Basics

1. Initialize repo and configure git basics:
    ```bash
    mkdir <repo_name>
    git init
    git config user.name "Your Name"
    git config user.email "YourEmail@example.com"
    ```

2. Add, commit and push the changes to the selected upstream:
    ```bash
    git add .
    git commit -m "Commit message"
    git push
    ```

3. List files that are being tracked by git (only the ones addded with git add or pushed):
    ```bash
    git ls-files
    ```

## Commit

1. Delete local commits till the last pushed one:
    ```bash
    git reset --hard origin/<branch_name>
    ```

## Branch

1. Create new branch and copy the contents to that branch:
    ```bash
    git branch <branch_name>
    git checkout <branch_name>
    ```

2. First push to new branch:
    ```bash
    git push --set-upstream origin <branch_name>
    ```

3. Swap between branches without making changes on them:
    ```bash
    git switch <branch_name>
    ```

4. Check differences between braches:
    ```bash
    git diff <reference_branch_name> <branch_name>
    ```

    Note: Git diff will show in green the adittions to the reference branch and in red the deletions to the reference branch.

## Merge

1. Basic merge:
    ```bash
    git switch main
    git merge <branch_name_to_merge>
    git push
    ```

## Rebase

1. Make a basic rebase between branches:
    ```bash
    git rebase <source_branch_name> <destination_branch_name>
    git push
    ```
    Note: The git rebase comand will "merge" the source branch to the destination so that both branches are equal. Example: You have made changes in the main branch and you want to update the development branch you have to do:  
    ```bash
        git rebase main development 
    ```
2. Rebase with conflicts:
    ```bash
    git rebase <source_branch_name> <destination_branch_name>
    ```
    Once git stops and shows the conflict, we have to solve it and do:
    ```bash
    git add .
    git rebase --continue
    ```
    If you need to abort:
    ```bash
    git rebase --abort
    ``` 