# 1. Tech Setup

This is how I set my computer to code

## 1.1. Considerations

- This example is in Mac probably if you use other system change some stuff.
- External install I only share you the links to understand how install it, I don't explaing how to install each one in this post.

---

## 1.2. Customize a Term

First of all I liked to set a good terminal with a some relevant things, like branch of git and also personalized a little bit.

For this case I use iTerm2, you can find how download here: <https://iterm2.com/>

After that you need to install oh-my-zsh this is how I manage the iTerm personalization, you can find how to download here: <https://ohmyz.sh/>

If you already install these 2 tools, we continue with the personalization, you need to follow next steps:

- Open iTerm2
- Go to Preferences>General>Closing and disabled all the options, this is remove the verification when you closed the terminal with more than one pestaña.
- Also in Preferences you can go to Profiles option and create new one, after that set the new profile as default.
- In this profile in general option, you can select Reuse previous session's directory to allow the terminal always open in the last route than you use iterm.
- Now you need to download this theme: <https://ethanschoonover.com/solarized>/ and import in the options colors inside your profile. And select the theme in the options, this set a customized UI for iTerm.
- And after that you can see a little bit different term.

But also you can change and do easier to use our terminal, this is using and change the .zshrc file to set some help commands or personalized colors when used Git. I share you my aggregation to .zshrc file and explain why is each line.

```shell
  #This line upload the colors to use in the next lines
  autoload -U colors promptinit && colors

  #This personalized the prompt of our terminal
  PROMPT='$fg[blue]%1~$reset_color $(git_prompt_info)$fg[yellow]> $reset_color'

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
  alias gpd="git pull origin develop"
  alias gpm="git pull origin master"

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
