# Lab Exercise 17: Visual Merge Conflict Resolution in VS Code

> **Objective**: Resolve merge conflicts using Visual Studio Code's 3-way Merge Editor and CodeLens conflict resolution decorators.

---

### Conflict Resolution Workflow in VS Code

1. Triggered conflicts flag files under **Merge Changes** in the Source Control panel.
2. CodeLens buttons appear directly above the conflict block:
   - **Accept Current Change**: Preserves local checked-out branch version (`HEAD`).
   - **Accept Incoming Change**: Overwrites local with the merging branch's version.
   - **Accept Both Changes**: Retains both snippets sequentially.
   - **Open in Merge Editor**: Opens the 3-pane visual resolver (Current, Incoming, Result).
3. Selected hybrid consensus (`Lab mode: hybrid`) removing all marker boundaries (`<<<<<<<`, `=======`, `>>>>>>>`).
4. Staged the resolved file (`+`) and committed cleanly without conflict residues.

- Visual workflow steps and log in [`output.txt`](output.txt).
