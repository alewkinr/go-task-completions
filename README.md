# go-task completions

Zsh completions for [go-task](https://github.com/go-task/task)

[![asciicast](https://asciinema.org/a/MZn6pzx7DUTMt1y3pCnEtNi1W.png)](https://asciinema.org/a/MZn6pzx7DUTMt1y3pCnEtNi1W)

## Usage
Completion for `task`

```bash
task <TAB>
```

Completion for options


```bash
task -<TAB>
```
For autocompletion of your global Taskfile, you need to use `gtask` or `run` commands.

## Installation

### [oh-my-zsh](http://github.com/robbyrussell/oh-my-zsh)

Clone the repository inside your oh-my-zsh repo:
```bash
git clone https://github.com/alewkinr/go-task-completions.git ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/task
```
> original from https://github.com/sawadashota/go-task-completions.git

Enable it in your .zshrc by adding it to your plugin list and reloading the completion:
```bash
plugins=(… task)
autoload -U compinit && compinit
```

### Global Taskfile autocompletion

Add `GLOBAL_TASKFILE` to your `.zshrc` file:
```bash
export GLOBAL_TASKFILE='/path/to/your/global/Taskfile.yml'
```

If you want to change task command behavior, you can overwrite it. Add this to you `.zshrc` file:
```bash
    function gtask() {
      # in example:
      task -t $GLOBAL_TASKFILE $@ -- $(pwd); 
    }
```