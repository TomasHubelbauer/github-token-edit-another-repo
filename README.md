# `GITHUB_TOKEN` edit another repository

GitHub Actions allow you to bring your own personal access token (PAT) or use
the out of the box PAT named `GITHUB_TOKEN` to hit the GitHub API, do stuff with
Git etc.

When it comes to custom PATs, GitHub at the moment has two types, legacy and
just PATs (which I will call modern because "just PATs" used to refer to the
legacy ones before the new ones came about).

Legacy PATs had configurable scopes that would allow the token to do stuff or
not and they were scoped to the entire user or organization, meaning they could
access all of their public repositories (and private if such scope was granted).
This is a very bad idea and it is surprising it made it out of the lab at all,
but it did and ~~soon after~~ it lived on for quite a while, unfortunately.
But nowadays, GitHub have rectified this design and introduced the moderm PATs
which have permissions one can adorn them with as well as the ability to scope
to a single repository or a set of repositories.

I don't know how the integration PAT that comes built-in with GitHub Actions
works but since there is a key named `permissions` that one could in their
GitHub Actions workflows, I assume - purely based on the nomenclature - that it
is the modern type PAT.

If that's the case, changes are it is scoped to the repository it is created and
later revoked for - the one which the workflow is in.

But I don't know this for a fact and I am working on something right now which
would benefit from being able to edit another repository's metadata from within
a GitHub Actions workflow of a different repository.

So I need to find out which is which.
I will add a workflow to this repository and try to hit the GitHub API in it and
edit the repository metadata (description and home page) of another repository.
Once I know what happens, I will update this post and capture the results.
