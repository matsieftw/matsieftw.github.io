---
layout: post
title: Clearing Your Shell With Only The Return Key
---
I am a die hard command line user. I am not highly opinionated on whether or not everyone else should be working solely out of the command line, but my own personal idiosyncrasies kind of demand it -- I *hate* having multiple windows open. This means, I use a lot of tabs and splits and my preferred text editor is Vim. I work from my terminal and I love it because it provides me with both simplicity (one window) and complexity (text editor, shell, [reddit browser](https://github.com/michael-lazar/rtv)).

## So Many Typos

That being said, I end up entering a lot of commands into my terminal and now I've got a cluttered screen where all my relevant text is at the bottom. I've gotten into the habit of typing `clear` _a lot_. But this leaves room for typos...sometimes so many typos. Ugh. SO. MANY. TYPOS.

![Clear Shell Typo - MatsieFTW!]({{ site.baseurl }}/images/clearScreenTypo.png)

My deskmate is a 'return key' guy. He just presses return a bunch until he's got some whitespace on the screen and continues running commands. This got me thinking on how to combine these two methods to make one Super Method<sup>TM</sup>.

## Enter the Return Key Clear Shell Script

So now I looked for a solution that cleared my shell whenever I pressed the return key twice. And behold, [return\_key\_clear.sh](https://github.com/matsieftw/matsie-tools/tree/master/return-key-clear):
```
declare empty_counter=0

precmd_hook() {
    if [[ $empty_count -gt 1 ]]; then
        /usr/bin/clear
        let empty_count=0
    fi

    let empty_count=$empty_count+1
}

preexec_hook() {
    let empty_count=0
}

autoload -U add-zsh-hook

add-zsh-hook precmd precmd_hook
add-zsh-hook preexec preexec_hook
```

<small>**This shell script works reliably and predictably for `zsh` on both macOS and Ubuntu Linux.</small>

<small>**Update 2016-11-16 - The original version of this post used `MacOS` instead `macOS`. For this, I am eternally regretful of the internet points I lost. As we all know, they can never be regained.**