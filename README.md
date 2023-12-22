# downstreamable-buildkite-plugin

Easy adapter for embedding buildkite tests as downstream tests in other repositories.
This plugin functions by noticing when the current `${BUILDKITE_REPO}` is set to something other than the `repo_url` provided to this plugin,
then cloning and `cd`'ing into that newly-cloned directory as part of the `post-checkout` phase.
Simply put the following plugin stanza at the top of all of your pipelines that you wish to become downstreamable:

```
- staticfloat/downstreamable:
    repo_url: "https://github.com/org/repo"
```

### Advanced features

The location that the repository is checked out to can be customized with the `dir` argument.
The branch that is checked out can be customized with the `branch` argument.
If you need to customize the checkout a bit, you can create a `~/.buildkite/downstreamable.hook` file in your top-level repository, and it will be run once the repo has been cloned.
