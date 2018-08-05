---
layout: post
title: How I Learned to Love `tmux`
---

My coworker, [Paul](http://github.com/wheresmyjetpack) and I were discussing the virtues of [tmux](https://github.com/tmux/tmux) a few days ago and both of us were at a loss at to why it was useful. tmux brands itself as a "terminal multiplexer". It gives you the ability to have multiple terminals instances opened at once without having to use multiple windows. 

This seems useful at first, but both Paul and I use [iTerm2](https://www.iterm2.com/) as our terminal app and iTerm2 already provides tabbed windows and split panes. This weekend provided me with the motivation to learn tmux more fully and try it out in my workflow -- and boy am I enjoying it.

What's amazing about my change of heart is that I'm using tmux only in the most basic implementation right now. I use it to background apps and to afford myself more screen real estate on my cramped Macbook Air screen.

I now have a tmux session that handles my `top` and `rails server` screens and I don't have to worry about if my ssh connection breaks or about losing a little bit of screen real estate. I even keep a split in the session for man pages I'm looking at.

So why use it over iTerm2's splits and tabs? iTerm won't keep your session going. If you're pulling a particularly large repo or installing something big, iTerm could lose that connection and your session is over, as is that download. With tmux, you're not just getting a way to manage your multiple windows -- **you're gaining a way to manage multiple sessions**. And that makes a WORLD of difference once you incorporate it into your workflow.