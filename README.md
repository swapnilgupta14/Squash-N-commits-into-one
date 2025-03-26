## Steps to Squash the Last N Commits

1. **Start the Interactive Rebase**
   
   Run the following command, replacing `N` with the number of commits you want to squash:  
   ```bash
   git rebase -i HEAD~N
   ```
   Example: If you want to squash the last **3** commits, use:  
   ```bash
   git rebase -i HEAD~3
   ```

3. **Modify the Commit Actions**
   
   A window will open in the terminal displaying the last `N` commits.  
   - Press `I` to enter **insert mode** (if using Vim).  
   - Navigate using the **arrow keys**.  
   - Change **`pick`** to **`squash`** (`s`) for all commits except the first one.  
   - Press `ESC` to exit insert mode.  
   - Type `:wq` and press **Enter** to save and exit.

5. **Edit the Commit Message**
   
   - Git will now show all the commit messages.  
   - Remove unnecessary commit messages, keeping only the one you want.  
   - Optionally, modify the first commit's message.  
   - Press `ESC`, then type `:wq` and press **Enter** to save.

7. **Successful Rebase Message**
   
   If successful, you'll see an output like:  
   ```bash
   [detached HEAD 504aadf] add: new branch
   Successfully rebased and updated refs/heads/<your-branch>
   ```

## Notes:

- If you've already pushed the branch, use **force push** to update the remote repository:
  
  ```bash
  git push origin <your-branch> --force
  ```
- If you encounter conflicts, resolve them and continue the rebase:
  
  ```bash
  git rebase --continue
  ```
- To **abort** the rebase if needed:
  
  ```bash
  git rebase --abort
  ```
