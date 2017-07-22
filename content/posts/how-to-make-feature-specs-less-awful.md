---
title: "How to make feature specs less awful"
date: 2017-07-20
tags: [capybara, rails, rspec, testing]
categories: [programming, ruby]
---

Feature specs are the worst. Rails devs are nodding. This is a post I wish I had found before mebarking on my pursuit of a consistent legacy test suite that includes capybara feature specs.

## The Problem

The fundamental problem is that capybara boots your actual app in a separate process then runs the test instructions against that app to test interactions with it. 

As the test instructions go on your Rails app can be doing whatever it wants, so you get a dumpster fire of race conditions where your spec is expecting something to happen or be there but your app is still working on making that thing happen while the test moves on.

## The Solution

- Read this great {{% target_blank "article by Joe Ferris about capybara" "https://robots.thoughtbot.com/write-reliable-asynchronous-integration-tests-with-capybara" %}} and sweep your specs for culprits then implement the fixes Ferris recommends.
- Read this article (also by Thoughbot) about {{% target_blank "dealing with async JS in tests" "https://robots.thoughtbot.com/automatically-wait-for-ajax-with-capybara" %}} and add a call to `wait_for_ajax` after any ajax calls in your feature specs (assuming you're using jQuery for ajax calls).
- Use `let` not instance variables inside `before` blocks for two reasons:
  1. `let` is a method call and RSpec memoizes it and cleans up after you properly when you use it. Instance variables can stick around in memory in weird ways when you don't expect them to, especially when you're not explicitly handling cleaning them up yourself.
  2. It's {{% target_blank "best practice." "http://www.betterspecs.org/#let" %}}

Doing these things dramatically improved our test suite. You're on your own from here. Good luck!


