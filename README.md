# Customize your zsh prompt ⌨️


<img align="left" alt="Before configuration" width="400px" src="https://i.ibb.co/km0t2RY/Captura-de-ecr-2020-10-19-s-10-30-34.png" />
<img align="center" alt="After configuration" width="400px" src="https://i.ibb.co/F6j6Fyj/Captura-de-ecr-2020-10-19-s-10-33-39.png" />

Open zshrc config file using a text editor ` nano ~/.zshrc` in order to add costum configurations.

#### Including Git Branch Information

Load version control information

```
autoload -Uz vcs_info
precmd() { vcs_info }
```

Format the vcs_info_msg_0_ variable

```
zstyle ':vcs_info:git:*' formats '(*%b)'
```

Set up the prompt (with git branch name at the end)
```
setopt PROMPT_SUBST
PROMPT='%n ${PWD/#$HOME/~} ${vcs_info_msg_0_} > '
```

#### Adding Colors

There are two ways to represent colors: using a color of the list `[black, red, green, yellow, blue, magenta, cyan or white]` or a number between 0 and 255:

- **%F{color}Text%f:** changes "Text" color to the new color indicated (%F starts foreground color and %f stops foreground color)
- **%K{color}Text%k:** changes "Text" background color to the new color indicated (%K starts background color and %k stops background color)
- **%BText%b:** displays "Text" to bold (%B starts bold and %b stops bold)
- **%UText%u:** underlines "Text" (%U starts underline and %u stops underline)

Change the PROMPT set up to include color configuration:
```
PROMPT='%F{cyan}%n%f ${PWD/#$HOME/~} %B%F{green}${vcs_info_msg_0_}%f%b > '
```

#### Changing Shell Background

I used shell preferences to costumize shell background color and effects by changing the color opacity and blur to make a semi transparent effect.
