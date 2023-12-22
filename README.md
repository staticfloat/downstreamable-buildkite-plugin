# downstreamable-buildkite-plugin

Easy adapter for embedding buildkite tests as downstream tests in other repositories.
This plugin functions by noticing when the current `${BUILDKITE_REPO}` is set to something other than the `repo_url` provided to this plugin,
then cloning and `cd`'ing into that newly-cloned directory as part of the `post-checkout` phase.
Simply put the following plugin stanza at the top of all of your pipelines that you wish to become downstreamable:

```
staticfloat/downstreamable:
  repo_url: "https://github.com/org/repo"
```
