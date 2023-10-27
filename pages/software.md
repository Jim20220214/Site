# DOCUMENTATION 

[Home][Home]

### Terminal

#### ZSH

~/.zshrc
```zsh
# Store history in the directory where the shell session was started
# Define a colorful prompt
#-----
source "$HOME/.zsh/aliases.zsh"
#-----
setopt prompt_subst
#-----ALL COLORS
#PS1='%F{124}1%F{2}2%F{3}3%F{4}4%F{5}5%F{6}6%F{7}7%F{8}8%F{9}9%F{10}10%F{11}11%F{12}12%F{13}13%F{14}14%F{15}15%F{16}16%F{17}17%F{18}18%F{89}89%F{90}90%F{91}91%F{92}92%F{93}93%F{94}94%F{95}95%F{96}96%F{97}97%F{98}98%F{99}99%F{100}100%F{101}101%F{102}102%F{103}103%F{104}104%F{105}105%F{106}106%F{107}107%F{108}108%F{109}109%F{110}110%F{111}111%F{112}112%F{113}113%F{114}114%F{115}115%F{116}116%F{117}117%F{118}118%F{119}119%F{120}120%F{121}121%F{122}122%F{123}123%F{124}124%F{125}125%F{126}126%F{127}127%F{128}128%F{129}129%F{130}130%F{131}131%F{132}132%F{133}133%F{134}134%F{135}135%F{136}136%F{137}137%F{138}138%F{139}139%F{140}140%F{141}141%F{142}142%F{143}143%F{144}144%F{145}145%F{146}146%F{147}147%F{148}148%F{149}149%F{150}150%F{151}151%F{152}152%F{153}153%F{154}154%F{155}155%F{156}156%F{157}157%F{158}158%F{159}159%F{160}160%F{161}161%F{162}162%F{163}163%F{164}164%F{165}165%F{166}166%F{167}167%F{168}168%F{169}169%F{170}170%F{171}171%F{172}172%F{173}173%F{174}174%F{175}175%F{176}176%F{177}177%F{178}178%F{179}179%F{180}180%F{181}181%F{182}182%F{183}183%F{184}184%F{185}185%F{186}186%F{187}187%F{188}188%F{189}189%F{190}190%F{191}191%F{192}192%F{193}193%F{194}194%F{195}195%F{196}196%F{197}197%F{198}198%F{199}199%F{200}200%F{201}201%F{202}202%F{203}203%F{204}204%F{205}205%F{206}206%F{207}207%F{208}208%F{209}209%F{210}210%F{211}211%F{212}212%F{213}213%F{214}214%F{215}215%F{216}216%F{217}217%F{218}218%F{219}219%F{220}220%F{221}221%F{222}222%F{223}223%F{224}224%F{225}225%F{226}226%F{227}227%F{228}228%F{229}229%F{230}230%F{231}231%F{232}232%F{233}233%F{234}234%F{235}235%F{236}236%F{237}237%F{238}238%F{239}239%F{240}240%F{241}241%F{242}242%F{243}243%F{244}244%F{245}245%F{246}246%F{247}247%F{248}248%F{249}249%F{250}250%F{251}251%F{252}252%F{253}253%F{254}254%F{255}255%F{256}256'
#-----
#source "$HOME/.zsh/home.zsh"
#if home else if 
if [ "$(pwd)" = "$HOME" ]; then
    echo "Home sweet home, ~/.zshrc"
    PS1='%F{244}[%F{124}%*%F{244}] %F{166}%n%F{244}@%F{160}%m%F{172}%~ %F{178}<3 %F{244} %# '
else
    if [[ -f ./.zshrc ]]; then
        echo "Sourcing local .zshrc"
        source "./.zshrc"
    else
        echo "Local .zshrc not found, falling back to ~/.zshrc"
        PS1='%F{244}[%F{124}%*%F{244}] %F{166}%n%F{244}@%F{160}%m%F{172}%~ %F{178}</3 %F{244} %# '
    fi
fi
#-----
```
[currentFolder]/.zshrc
```zsh
autoload -U colors
autoload -U colors && colors
autoload -U compinit
autoload -U edit-command-line

setopt COMPLETE_IN_WORD
setopt APPEND_HISTORY
setopt INC_APPEND_HISTORY
setopt SHARE_HISTORY
setopt EXTENDED_HISTORY
setopt HIST_IGNORE_DUPS
setopt HIST_EXPIRE_DUPS_FIRST
setopt HIST_IGNORE_SPACE
setopt AUTO_CD
setopt NO_BEEP
setopt prompt_subst
setopt autopushd
setopt pushdminus
setopt pushdsilent
setopt pushdtohome

colors
compinit

DIRSTACKSIZE=8
HISTSIZE=5000
SAVEHIST=5000
HISTFILE=~/.history
MAILCHECK=0

EDITOR=nano

# source "$HOME/.zsh/aliases.zsh"
# source "$HOME/.zsh/completion.zsh"
# source "$HOME/.zsh/edit_command_line.zsh"
# source "$HOME/.zsh/tmux.zsh"
# source "$HOME/.zsh/git.zsh"
# source "$HOME/.zsh/prompt.zsh"
# source "$HOME/.zsh/rbenv.zsh"
# source "$HOME/.zsh/rust.zsh"
# source "$HOME/.zsh/rsvm.zsh"
# source "$HOME/.zsh/golang.zsh"
# source "$HOME/.zsh/rust.zsh"
# source "$HOME/.zsh/less.zsh"

# Source any extra config that should not be
# in the public dotfiles repo
if [ -f "$HOME/.zsh/extras.zsh" ]; then
  source "$HOME/.zsh/extras.zsh"
fi

if (( $+commands[direnv] )); then
  eval "$(direnv hook zsh)"
fi

# Basic prompt with just the current directory
#PS1='%n@%m %~ %# '

# More detailed prompt with current directory, time, and username
#PS1='%n@%m %~ %* %# '

# A colorful prompt with user, host, and current directory
#PS1='%F{green}%n@%m%f %F{blue}%~%f %# '

# Include Git branch information in the prompt
autoload -Uz vcs_info
precmd() {
    vcs_info
}
setopt prompt_subst
# PS1='%n@%m %F{red}%~%f ${vcs_info_msg_0_} %# '
PS1='%F{244}[%F{124}%*%F{244}] %F{166}%n%F{244}@%F{160}%m%F{172}%~ %F{178}${vcs_info_msg_0_} %F{244} %# '
# Use the "agnoster" theme (requires Powerline fonts and the "agnoster" Oh-My-Zsh theme)
ZSH_THEME="agnoster"


```

### Code/Text Editor

#### Sublime Command Line Interface [(ref)][ref_sublime]

Sublime Text includes a command line tool, subl, to work with files on the command line. This can be used to open files and projects in Sublime Text, as well working as an EDITOR for unix tools, such as git and subversion.

###### [Setup](#setup) {#nav_setup}
###### [Usage](#usage) {#nav_usage}
###### [Configuring as EDITOR](#configuring-as-editor) {#nav_configuring-as-editor}

##### Setup
Some operating systems and installation methods will require a configuration change to make subl available on the PATH.

`echo 'export PATH="/Applications/Sublime Text.app/Contents/SharedSupport/bin:$PATH"' >> ~/.zprofile`

##### Usage
To see the available flags, run subl --help. The available flags will vary per operating system – the following example is from Linux:
```
Sublime Text build 4131

Usage: subl [arguments] [files]         Edit the given files
   or: subl [arguments] [directories]   Open the given directories
   or: subl [arguments] -- [files]      Edit files that may start with '-'
   or: subl [arguments] -               Edit stdin
   or: subl [arguments] - >out          Edit stdin and write the edit to stdout

Arguments:
  --project <project>:    Load the given project
  --command <command>:    Run the given command
  -n or --new-window:     Open a new window
  --launch-or-new-window: Only open a new window if the application is open
  -a or --add:            Add folders to the current window
  -w or --wait:           Wait for the files to be closed before returning
  -b or --background:     Don't activate the application
  --safe-mode:            Launch using a sandboxed (clean) environment
  -h or --help:           Show help (this message) and exit
  -v or --version:        Show version and exit

Filenames may be given a :line or :line:column suffix to open at a specific
location.
```

##### CONFIGURING AS EDITOR
To use Sublime Text as the editor for many commands that prompt for input, set your EDITOR environment variable:  
`export EDITOR='subl -w'`
>Specifying -w will cause the subl command to not exit until the file is closed.

-----
[ref_sublime]: https://www.sublimetext.com/docs/command_line.html
[Home]: https://jim20220214.github.io/Site/

