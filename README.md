# itsJCs-agnoster.zsh-theme

Follow the full terminal setup guide here: 

## Customize your prompt view

By default prompt has these segments: `prompt_status`, `prompt_context`, `prompt_timestamp`, `prompt_virtualenv`, `prompt_dir`, `prompt_git`, `prompt_end` in that particular order.

If you want to add, change the order or remove some segments of the prompt, you can use array environment variable named `AGNOSTER_PROMPT_SEGMENTS`.

## Examples

###  Custom Text in Prompt
A small demo of the dummy custom prompt segment, which has been created with help of the built-in `prompt_segment()` function from Agnoster theme:
```
# prompt_segment() - Takes two arguments, background and foreground.
# Both can be omitted, rendering default background/foreground.

customize_agnoster() {
  prompt_segment 'red' '' ' ⚙ ⚡⚡⚡ ⚙  '
}
```

### Add timestamp
Add timestamp to prompt by adding the `prompt_timestamp` to the segments:
```
typeset -aHg AGNOSTER_PROMPT_SEGMENTS=(
    prompt_status
    prompt_context
    prompt_timestamp
    prompt_virtualenv
    prompt_dir
    prompt_git
    prompt_end
)
```
You can also modify the fore and background of the segment: 
```
prompt_timestamp() {
  prompt_segment black white '%*'
}
```

### Print out Working Dir or Current Dir
```
# Dir: current directory only
prompt_dir() {
  prompt_segment blue white ' %c '
}
```
```
# Dir: working directory path
prompt_dir() {
  prompt_segment blue white ' %~ '
}
```
