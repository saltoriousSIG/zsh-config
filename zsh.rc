# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# Path to your oh-my-zsh installation.
export ZSH="$HOME/.oh-my-zsh"

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="robbyrussell"

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in $ZSH/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment one of the following lines to change the auto-update behavior
# zstyle ':omz:update' mode disabled  # disable automatic updates
# zstyle ':omz:update' mode auto      # update automatically without asking
# zstyle ':omz:update' mode reminder  # just remind me to update when it's time

# Uncomment the following line to change how often to auto-update (in days).
# zstyle ':omz:update' frequency 13

# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# You can also set it to another string to have that shown instead of the default red dots.
# e.g. COMPLETION_WAITING_DOTS="%F{yellow}waiting...%f"
# Caution: this setting can cause issues with multiline prompts in zsh < 5.7.1 (see #5765)
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"

# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"
# My aliases

alias sudo='sudo '
alias keys='cat ~/.keys/githubkeys.txt | xclip -sel clip'
alias openzshconf='nvim ~/.zshrc'
alias nod='nvim .'
alias vrus='cd /media/sigi-dev/Wurk/VerusMktPlce'
alias igame='cd /media/sigi-dev/Wurk/Internet_Game/'

typeset -A folder_data=(devbase GUB-dev/gub-dev-beta devtournament GUS-Tournament/gus-tournament devarena GUSArena/gus-arena devlib GUSComponentLib devcontract GUS_Diamond/GUS-diamond-hardhat devhome GUSHome/GUSHome devserver GUSServer-dev/server prodclient GUB-prod/gub-client prodserver GUB-prod-server/production stagingserver GUB-prod-server/staging prodtournament GUSTournament-Prod/GUSTournament-Production prodarena GUSArena-Prod/GUSArena-Production)


ppb () {
  if [[ "$1" == "" ]]; then
    cd /media/sigi-dev/Wurk/pepeball/
    return 
  fi
}

gus () { 
  if [[ "$1" == "" ]]; then
    cd /media/sigi-dev/Wurk/GUStakes-gey/
    return
  fi
  if [[ "$2" == "base" ]]; then
    if [[ "$3" == "launch" ]]; then
      cd /media/sigi-dev/Wurk/GUStakes-gey/${folder_data[$1$2]}/client && npm start && gnome-terminal -- bash -c "cd /media/sigi-dev/Wurk/GUStakes-gey/${folder_data[$1$2]}/server && npm run dev" &
      return
    else
      cd /media/sigi-dev/Wurk/GUStakes-gey/${folder_data[$1$2]}/client && nvim . && gnome-terminal -- bash -c "cd /media/sigi-dev/Wurk/GUStakes-gey/${folder_data[$1$2]}/server && nvim ." 
      return
    fi
  fi 
    
  if [[ "$3" == "launch" ]]; then
    cd /media/sigi-dev/Wurk/GUStakes-gey/${folder_data[$1$2]} && npm run dev 
    return
  elif [[ "$3" == "edit" ]]; then
    cd /media/sigi-dev/Wurk/GUStakes-gey/${folder_data[$1$2]} && nvim .  
    return
  else
    cd /media/sigi-dev/Wurk/GUStakes-gey/${folder_data[$1$2]}  
    return
  fi  
}


typeset -A sinks
soundout() {
  pactl list short sinks | while read -r line; do
    # Split the line into an array using default whitespace delimiters
    line_array=(${(z)line})

    # Extract the ID and Name
    sink_id=$line_array[1]
    sink_name=$line_array[2]

    # Do something with the variables
    if [[ "$sink_name" == "alsa_output.pci-0000_12_00.3.analog-stereo" ]]; then
      sinks[speakers]="$sink_id"
    elif [[ "$sink_name" == "alsa_output.usb-SteelSeries_SteelSeries_Arctis_1_Wireless-00.analog-stereo" ]]; then
      sinks[headphones]="$sink_id"
    fi
  done 
  pactl set-default-sink "$sinks[$1]"

}


export NVM_DIR="/home/sigi-dev/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"  # This loads nvm

# bit
export PATH="$PATH:/home/sigi-dev/bin"
# bit end
export PATH=/home/sigi-dev/go/bin:$PATH
export PATH="/home/sigi-dev/.local/share/solana/install/active_release/bin:$PATH"

eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
