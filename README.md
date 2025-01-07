## showcase of helix' filepicker inconsistency with git.

### steps in helix.

- cd into `./folder-A`.
- open `helix`.
- press `space + F`.

Files from `./.folder-B` appear in filepicker.

### steps in git.

- cd into `./folder-A`.
- run `find . | git check-ignore --no-index -v --stdin`.

Line `folder-A/.gitignore:2:*	./ignored-folder/ignored-subfolder.link` means, what symlink is ignored.

### steps in git (interactive).

- run `git rm -r --cached .`.
- run `git add .`.
- run `git status`.

Git will print ignored files as deleted.

### note.

Ignored files are in the repo, because they were added with `git add -f` command.
