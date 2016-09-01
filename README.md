# Cap Complete

Basically a clone of: https://github.com/nyarly/fish-rake-complete

When using cap, it can be kind of a hassle to remember all the weird, inconsistently named tasks you're working with. Was it `cap reboot:server` or `cap servers:reboot`?

At the same time, in a project of any significant size `cap -T` can take a while to run -
certainly too long to use in a completion.
Worse, each project (rightly) defines it's own list of tasks,
so a standard set of completions don't really make sense.

Paradox!
We're stuck with looking up the tasks we want and relying on fish's (awesome) history completions, right?

Not so.
The magic of caching to the rescue.

This plugin will automatically feed you completions for the local-most Capfile,
updating them either when that file changes
or if you call `zap_cap_cache`
(for instance, because you needed to update `lib/ill_advised_server_management.rb`.)

# Doesn't work on OS X?

OS X doesn't have an md5sum command, but you can easily emulate it for purposes
of this plugin by using:

```
function md5sum
  md5
end
funcsave md5sum
```
