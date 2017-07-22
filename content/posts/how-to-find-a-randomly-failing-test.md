---
title: "How to find a randomly failing RSpec test"
date: 2017-07-19
tags: ["rails", "rspec", "testing"]
categories: ["programming", "ruby"]
---

## The Problem

You develop your feature, running tests along the way and everything's working fine. You push right to CI without running the whole test suite (because it takes forever), then FAIL. But all the tests I ran were working! What gives? 

You have some tests that only fail when run in a certain order.

## The Solution

### {{% target_blank "RSpec Bisect" "https://relishapp.com/rspec/rspec-core/docs/command-line/bisect" %}}

It's a utility included with rspec that automates the process of finding the minimum command to reproduce the test failure, so you can debug and fix it without running a ton of slow tests every time.

You use it by adding `--bisect` to the end of a command you know will produce a failing spec, like:

```bash
rspec spec/controllers --seed 1234 --bisect
```

It will give you some weird output like:

```bash
The minimum command to reproduce is 

rspec spec 'some_thing_spec.rb[1:1:2]', 'another_bad_spec.rb[1:2:1:1]'
```

Use RSpec bisect to find the culprit. Watch {{% target_blank "this video about rspec bisect" "https://thoughtbot.com/upcase/videos/rspec-bisect" %}} by Thoughtbot to learn how to use it.
