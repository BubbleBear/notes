What you want to is to ignore changes on tracked files. This cannot achieved (as Charles Bailey says) correctly, neither with .gitignore nor with .git/info/exclude.

You'll need to use git update-index:

    git update-index --assume-unchanged build/conf/a.conf
    git update-index --assume-unchanged build/conf/b.conf

will achieve what you want: the files are always assumed unchanged.

If you want to track changes in these files again, use --no-assume-unchanged.

Finally, if you want to know which files are currently in the --assume-unchanged mode, ask git for

    git ls-files -v | grep -e "^[hsmrck]"

---

[reference](https://stackoverflow.com/questions/10879783/git-doesnt-ignore-2-specifically-named-files)