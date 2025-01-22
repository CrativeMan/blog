---
title: CLH - A digital Helper
description: 
date: 2024-11-30
categories:
  - personal
  - dev
published: true
---

## A simple tool to help

Today i am starting on a project that hopefully will help me develope more projects and just organize and handle my workflows alot easier.
CLH or CrativeLifeHelper is going to be a ever expanding cli tool that will automate simple and repetetive tasks all in one place. Simple tasks like: 

- publishing new posts to this blog
- updating my nixos config
- backing up my vaults and passwords etc
- many more to come

## Implementation

I want to write this thing in the amazing beautiful language of [golang](https://go.dev) and i want to use the [huh](https://github.com/charmbracelet/huh) tui library from **charmbracelet** because it is really beautiful and easy to use.
I want to have a clean and expandable codebase so im going to split the code into modules, for reusability and efficiency.

I am using nix flakes for the deploying again, just because i am on nixos and i really love how easy it is to just install it in my system by just using flake inputs.
