# Add the Tableau workbook to GitHub

This project already has a public repository: https://github.com/brian-hua312/Chicago-Crime-Visuals

The README, analysis checklist, and Git LFS configuration are already on GitHub. **Do not create a second repository.**

## Upload the packaged Tableau workbook

1. Install and sign in to [GitHub Desktop](https://desktop.github.com/).
2. Install [Git LFS](https://git-lfs.com/) if necessary, then run `git lfs install` in Terminal or PowerShell.
3. In GitHub Desktop, select **File > Clone repository** and choose `brian-hua312/Chicago-Crime-Visuals`.
4. Download and extract the supplied project ZIP. Copy `Chicago_Crime_Analytics.twbx` into the top level of your cloned repository folder.
5. Confirm the repository's `.gitattributes` file has this line: `*.twbx filter=lfs diff=lfs merge=lfs -text`. This file has already been added to GitHub.
6. Confirm Git LFS recognizes the workbook after staging it. Run `git lfs ls-files` after the commit to confirm it is LFS tracked.
7. In GitHub Desktop, commit with the message `Add packaged Tableau workbook` and select **Push origin**.
8. Open the repository on GitHub and check that you can download the complete workbook.
9. Update the README to replace the temporary "not yet uploaded" text with a working workbook link.

If LFS is unavailable or the file is being committed as a regular Git object, stop before committing and correct the configuration.

## Next improvements

- Export screenshots from Tableau and add them to `images/`.
- Review the source extract and worksheet filters before adding quantified findings.
- Add a Tableau Public link only if the project and its embedded data are appropriate to share publicly.
