# fzf-git
Just a wrapper to make it behave like a omzsh/zinit plugin

<!-- 
https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts
-->


### List of bindings

* <kbd>CTRL-G</kbd><kbd>CTRL-F</kbd> for **F**iles
* <kbd>CTRL-G</kbd><kbd>CTRL-B</kbd> for **B**ranches
* <kbd>CTRL-G</kbd><kbd>CTRL-T</kbd> for **T**ags
* <kbd>CTRL-G</kbd><kbd>CTRL-R</kbd> for **R**emotes
* <kbd>CTRL-G</kbd><kbd>CTRL-H</kbd> for commit **H**ashes
* <kbd>CTRL-G</kbd><kbd>CTRL-S</kbd> for **S**tashes
* <kbd>CTRL-G</kbd><kbd>CTRL-L</kbd> for ref**l**ogs
* <kbd>CTRL-G</kbd><kbd>CTRL-W</kbd> for **W**orktrees
* <kbd>CTRL-G</kbd><kbd>CTRL-E</kbd> for **E**ach ref (`git for-each-ref`)


> [!WARNING]
> You may have issues with these bindings in the following cases:
>
> * <kbd>CTRL-G</kbd><kbd>CTRL-B</kbd> will not work if
>   <kbd>CTRL-B</kbd> is used as the tmux prefix
> * <kbd>CTRL-G</kbd><kbd>CTRL-S</kbd> will not work if flow control is enabled,
>   <kbd>CTRL-S</kbd> will freeze the terminal instead
>     * (`stty -ixon` will disable it)

> [!TIP]
> To workaround the problems, you can use
> <kbd>CTRL-G</kbd><kbd>*{key}*</kbd> instead of
> <kbd>CTRL-G</kbd><kbd>CTRL-*{KEY}*</kbd>.
>

> [!IMPORTANT]
> If zsh's `KEYTIMEOUT` is too small (e.g. 1), you may not be able
> to hit two keys in time.

> [!NOTE]
> Each binding is backed by `_fzf_git_*` function so you can do something like
> this in your shell configuration file.
>
> ```sh
> gco() {
>   _fzf_git_each_ref --no-multi | xargs git checkout
> }
> 
> gswt() {
>   cd "$(_fzf_git_worktrees --no-multi)"
> }
> ```

> [!TIP]
> ### Inside fzf
> 
> * <kbd>TAB</kbd> or <kbd>SHIFT-TAB</kbd> to select multiple objects
> * <kbd>CTRL-/</kbd> to change preview window layout
> * <kbd>CTRL-O</kbd> to open the object in the web browser (in GitHub URL scheme)
