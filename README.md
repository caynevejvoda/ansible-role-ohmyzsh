# Ansible Role: Oh My ZSH

[![CI](https://github.com/NakashiUGS/ansible-role-ohmyzsh/workflows/CI/badge.svg?event=push)](https://github.com/NakashiUGS/ansible-role-ohmyzsh/actions?query=workflow%3ACI)

This role installs ZSH and Oh My Zsh, change the default shell to ZSH and configure it.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

It is possible to install and configure ohmyzsh for multiple users.

    user: 
      - root

To allow custom plugins, set the variable to true and specify the url's and names.

    custom_plugins: false
    plugin_urls:
      - https://github.com/zsh-users/zsh-autosuggestions.git
      - https://github.com/zsh-users/zsh-syntax-highlighting.git
    plugin_names:
      - zsh-autosuggestions
      - zsh-syntax-highlighting


The zsh config file is created using a jinja template. To configure this, all options are available as variables. The default values correspond to the default .zshrc.

    ZSH_THEME: agnoster
    ZSH_THEME_RANDOM_CANDIDATES_BOL: false
    CASE_SENSITIVE: false
    HYPHEN_INSENSITIVE: false
    DISABLE_AUTO_UPDATE: false
    DISABLE_UPDATE_PROMPT: false
    UPDATE_ZSH_DAYS: false
    DISABLE_MAGIC_FUNCTIONS: false
    DISABLE_LS_COLORS: false
    DISABLE_AUTO_TITLE: false
    ENABLE_CORRECTION: false
    COMPLETION_WAITING_DOTS: false 
    DISABLE_UNTRACKED_FILES_DIRTY: false
    HIST_STAMPS: false
    ZSH_CUSTOM_BOL: false
    ZSH_CUSTOM: /path/to/new-custom-folder
    PLUGINS: 
    SOURCE: $ZSH/oh-my-zsh.sh
    MANPATH_BOL: false
    MANPATH: '"/usr/local/man:$MANPATH"'
    LANG_BOL: false
    LANG: en_US.UTF-8
    PREFERRED_EDITOR_BOL: false
    PREFERRED_EDITOR: |
      if [[ -n $SSH_CONNECTION ]]; then
        export EDITOR='vim'
      else
        export EDITOR='mvim'
      fi
    ARCHFLAGS_BOL: false
    ARCHFLAGS: '"-arch x86_64"'
    CUSTOM_OPTIONS: |
      # Example aliases
      # alias zshconfig="mate ~/.zshrc"
      # alias ohmyzsh="mate ~/.oh-my-zsh"

The user for whom ZSH is to be installed and configured.

## Dependencies

None.
## Example Playbook

    - hosts: all
      roles:
        - nakashiugs.ohmyzsh
## License

MIT

## Author Information

This role was created in 2022 by Cayne Vejvoda.