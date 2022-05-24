# Ansible Role: Oh My ZSH

[![CI](https://github.com/caynevejvoda/ansible-role-ohmyzsh/workflows/CI/badge.svg?event=push)](https://github.com/caynevejvoda/ansible-role-ohmyzsh/actions?query=workflow%3ACI)

This role installs ZSH and Oh My Zsh, change the default shell to ZSH and configure it.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

It is possible to install and configure ohmyzsh for multiple users.

    ohmyzsh_user: 
      - root

The zsh config file is created using a jinja template. To configure this, all options are available as variables. The default values correspond to the default .zshrc.

    ohmyzsh_path: false
    ohmyzsh_zsh_theme: robbyrussell
    ohmyzsh_zsh_theme_random_candidates: false
    ohmyzsh_case_sensitive: false
    ohmyzsh_hyphen_insensitive: false
    ohmyzsh_update_mode: false
    ohmyzsh_update_zsh_days: false
    ohmyzsh_disable_magic_functions: false
    ohmyzsh_disable_ls_colors: false
    ohmyzsh_disable_auto_title: false
    ohmyzsh_enable_correction: false
    ohmyzsh_completion_waiting_dots: false
    ohmyzsh_disable_untracked_files_dirty: false
    ohmyzsh_hist_stamps: false
    ohmyzsh_zsh_custom: false
    ohmyzsh_plugins: []
    ohmyzsh_plugin_urls: []
    ohmyzsh_source: $ZSH/oh-my-zsh.sh
    ohmyzsh_manpath: false
    ohmyzsh_lang: false
    ohmyzsh_preferred_editor: |
    ohmyzsh_archflags: false
    ohmyzsh_custom_options: |

### Example Role Variables 

    ohmyzsh_user:
      - root
      - alice
      - bob
    ohmyzsh_path: $HOME/bin:/usr/local/bin:$PATH
    ohmyzsh_zsh_theme: agnoster
    ohmyzsh_zsh_theme_random_candidates: '"robbyrussell" "agnoster"'
    ohmyzsh_case_sensitive: true
    ohmyzsh_hyphen_insensitive: true
    ohmyzsh_update_mode: disabled
    ohmyzsh_update_zsh_days: 13
    ohmyzsh_disable_magic_functions: true
    ohmyzsh_disable_ls_colors: true
    ohmyzsh_disable_auto_title: true
    ohmyzsh_enable_correction: true
    ohmyzsh_completion_waiting_dots: true
    ohmyzsh_disable_untracked_files_dirty: true
    ohmyzsh_hist_stamps: '"mm/dd/yyyy"'
    ohmyzsh_zsh_custom: "/path/to/new-custom-folder"
    ohmyzsh_plugins:
      - zsh-autosuggestions
      - zsh-syntax-highlighting
    ohmyzsh_plugin_urls:
      - https://github.com/zsh-users/zsh-autosuggestions.git
      - https://github.com/zsh-users/zsh-syntax-highlighting.git
    ohmyzsh_source: $ZSH/oh-my-zsh.sh
    ohmyzsh_manpath: '"/usr/local/man:$MANPATH"'
    ohmyzsh_lang: en_US.UTF-8
    ohmyzsh_preferred_editor: |
      if [[ -n $SSH_CONNECTION ]]; then
        export EDITOR='vim'
      else
        export EDITOR='mvim'
      fi
    ohmyzsh_archflags: '"-arch x86_64"'
    ohmyzsh_custom_options: |
      alias ls="ls -l"
      alias la="ls -la"
## Dependencies

None.
## Example Playbook
    ---
    - hosts: all
      roles:
        - caynevejvoda.ohmyzsh
## License

MIT

## Author Information

This role was created in 2022 by Cayne Vejvoda.