# 1. Tech Setup

This is how I set up my computer to code

## 1.1. Considerations

- This example is in Mac probably if you use other system change some stuff.
- For external installs I only share you the links to understand how install it, I don't explaing how to install each one in this post.

---

## 1.2. Customize a Term

First of all, I wanted to set a good terminal with a some relevant things, like the current git's branch and, also customize it a little bit deeper.

For this case I use iTerm2, you can find how to download it here: <https://iterm2.com/>

After that you need to install oh-my-zsh this is how I manage the iTerm personalization, you can find how to download it here: <https://ohmyz.sh/>

If you already install these 2 tools, we continue with the personalization, you need to follow next steps:

- Open iTerm2
- Go to Preferences>General>Closing and disable all the options, this will remove the verification when you close the terminal while having more than one tab.
- Also, in Preferences you can go to Profiles option and create a new one, after that set the new profile as default.
- Now you need to download this theme: <https://ethanschoonover.com/solarized>/ and import it in the colors option inside your profile. Now select the theme in the options, this will set a customized UI for iTerm.
- Aftor you make all the previous changes you will see a little bit different term.

But also you can change and do easier to use our terminal, this is using and change the .zshrc file to set some help commands or personalized colors when using Git. I share with you what I added to my .zshrc file and explain what each line/block does.

```shell
  #This line upload the colors to use in the next lines
  autoload -U colors promptinit && colors

  #This personalized the prompt of our terminal
  PROMPT='%F{blue}%1~%f $(git_prompt_info)%F{yellow}>%f ' 

  # Alias to work with git and git flow, this help a lot to abbreviate some commands
  alias ga='git add'
  alias gc='git commit -m'
  alias gst='git status'
  alias gr='git rebase'
  alias gch='git checkout'
  alias feature_start='git flow feature start'
  alias feature_finish='git flow feature finish'
  alias release_finish='git flow release finish'
  alias release_start='git flow release start'
  alias hotfix_start='git flow hotfix start'
  alias hotfix_finish='git flow hotfix finish'

  # You can use take NAME_FOLDER then this method create and move to this new folder
  function take() {
    mkdir $1
    cd $1
  }

  # Git theme, the next lines are only for personalized Git
  ZSH_THEME_GIT_PROMPT_PREFIX="%{$fg[yellow]git:$reset_color$fg[green]%}"
  ZSH_THEME_GIT_PROMPT_SUFFIX="%{$reset_color%} "

  ZSH_THEME_GIT_PROMPT_DIRTY=" %{$fg[red]%}✗%{$reset_color%}"
  ZSH_THEME_GIT_PROMPT_CLEAN=" %{$fg[green]%}✔%{$reset_color%}"
  ZSH_THEME_GIT_PROMPT_ADDED=" %{$fg[green]%}✚{$reset_color%}"
  ZSH_THEME_GIT_PROMPT_MODIFIED=" %{$fg[yellow]%}⚑{$reset_color%} "
  ZSH_THEME_GIT_PROMPT_DELETED=" %{$fg[red]%}✖{$reset_color%} "
  ZSH_THEME_GIT_PROMPT_RENAMED=" %{$fg[blue]%}▴{$reset_color%} "
  ZSH_THEME_GIT_PROMPT_UNMERGED=" %{$fg[cyan]%}§{$reset_color%} "
  ZSH_THEME_GIT_PROMPT_UNTRACKED=" %{$fg[grey]%}◒{$reset_color%} "

  # Colors vary depending on time lapsed.
  ZSH_THEME_GIT_TIME_SINCE_COMMIT_SHORT="%{$fg[green]%}"
  ZSH_THEME_GIT_TIME_SHORT_COMMIT_MEDIUM="%{$fg[yellow]%}"
  ZSH_THEME_GIT_TIME_SINCE_COMMIT_LONG="%{$fg[red]%}"
  ZSH_THEME_GIT_TIME_SINCE_COMMIT_NEUTRAL="%{$fg[yellow]%}"

  # Format for git_prompt_long_sha() and git_prompt_short_sha()
  ZSH_THEME_GIT_PROMPT_SHA_BEFORE="%{$fg[white]%}[%{$fg[yellow]%}"
  ZSH_THEME_GIT_PROMPT_SHA_AFTER="%{$fg[white]%}]"
```
