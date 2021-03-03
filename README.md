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
  alias gc='git commit'
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

If you see the aliases in some of them we use git flow, for those aliases to work you first need to install hoombrew and then git flow, you can see how to install hombrew here: https://brew.sh/index_es, after you installed homebrew you can install git flow by pasting the next line of code on your terminal:

```shell
brew install git-flow
```

## 1.3 VS Code Extensions

For this tech setup we use the popular text editor VS Code, this is my favorite editor to work, I think it is the best in the market rigth now, but obviously it is a preference, if you are able to try VS Code the following extensions will help you to work better in some technologies. To get started, you need to install VS Code. You can see how install it here: https://code.visualstudio.com/download

When VS Code is already installed, you need to go to the left bar and click on the extensions button, and in the search field look for Settings Sync, once it appears, click it and now you will see an install button, now proceed to install it by clicking that button. Once Settings Sync is already installed, inside VS Code you will see  a new opened tab where you can see something related to Setting Sync. In this new tab you will see a link that says: "Download Public Gist", you can click on that link and it will open an input field, in that input field you need to paste the following id: 705031a080ec8d17a8ae37a83587a826 and then press the enter key. After that, some things will start downloading on your computer, the following extensions will be installed:

- Auto Close Tag: This helps you to close every html tag automatically.

- Bracket Pair Colorizer: This helps you to easily see where a bracket closes.

- C/C++: This is an extension to work with C/C++, but if you don't work with that language, you can uninstall that extension.

- Color highlight: With this extension you can see the color of any hex value.

- Community Material Theme: This helps to VS Code look better that's my favourite but you can find other different themes that you like.

- env-cmd-file-syntax: This only helps to make the .env files look beautiful.

- ES7 React/Redux/GraphQl Snippets: You can write some react code with only a few steps, it helps with repeated code.

- ES Lint: I think this is one of the most useful tools because it helps us to mantain a cleaner code. We use the airbnb convention for JS.

- GitLens: This tool shows you who wrote some code.

- Import Cost: This tool shows you the size of imports in JS.

- Markdown Shortcuts, Markdown Theme Kit and markdownlint: This 3 tools are useful if you use markdown to write documentation.

- Prettier: This corrects some code to mantain a code with a base of conventions.

- Ruby, Ruby on Rails and VSCode Ruby: These 3 tools help you when you are working with the Ruby language.

- Trailing spaces: This extension shows all the unnecessary spaces in your code.

- Settings Sync: This is for saving your VS Code config in your Github Gists and share it with other people.

I use all those extensions in my day to day as a Developer, some of them probably won't be useful for you but other sure will be. Also, note that the description for each extensions is very brief so if you want you can look them up on Google and learn how to use them.
