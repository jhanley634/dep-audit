
`dep-audit` will audit a project's dependencies,
looking for permissive deps which have new versions available.

def: A permissive dependency is a `requirements.txt` entry
of the form `foo >= 1.2.3`.

If e.g. foo version 1.2.5 is now available,
the audit will suggest revising the requirements.txt file to reflect that.
This tells users of your package about version combinations they
might sensibly pin, while still encouraging the adoption of updates.
Ruling out ancient versions will reduce the search space,
allowing faster solve times when computing the transitive deps.

# Usage

```bash
$ pip install --upgrade -r requirements.txt
$ dep-audit
```
Then make zero or more edits as needed, and commit.
