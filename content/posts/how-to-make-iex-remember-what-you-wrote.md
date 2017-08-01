+++
title = "How to make Iex remember what you wrote"
date = 2017-07-21
tags = ["elixir", "iex"]
categories = ["programming", "tools"]
+++

You might be in the habit of just pressing `up` to get previous things you wrote in a console. If you're used to ruby, this works in a rails console or `irb` session, too.

Today I learned how to make the elixir command-line shell thing remember what you wrote in the same way. It works for erlang 20.x and up. Add this line to your shell profile:

```bash
export ERL_AFLAGS="-kernel shell_history enabled"
```

🙂
