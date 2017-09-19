# ansible-macos-sublime
Ansible role to manage a sublime installation on macOS.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-sublime.svg)](https://travis-ci.org/feffi/ansible-macos-sublime) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-sublime/total.svg)](https://github.com/feffi/ansible-macos-sublime) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-sublime.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-sublime) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-sublime.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-sublime) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-sublime.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-sublime) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-sublime/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-sublime.git
  name: feffi.macos-sublime
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
---
macos_sublime:
  # The Sublime license to set
  license: ""

  # Settings to be placed in the Sublime user preferences
  preferences:
    theme: 'Soda Dark.sublime-theme'
    color_scheme: "ackages/Material Theme/schemes/Material-Theme.tmTheme"
    default_encoding: UTF-8
    default_line_ending: unix
    detect_indentation: false
    ensure_newline_at_eof_on_save: true
    file_exclude_patterns:
        - ".DS_Store"
        - "Desktop.ini"
        - "*.pyc"
        - "._*"
        - "Thumbs.db"
        - ".Spotlight-V100"
        - ".Trashes"
        - "*.aux",
        - "*.fls",
        - "*.idx",
        - "*.out",
        - "*.fdb_latexmk",
        - "*.pyc",
        - "*.pyo",
        - "*.exe",
        - "*.dll",
        - "*.obj",
        - "*.o",
        - "*.a",
        - "*.lib",
        - "*.so",
        - "*.dylib",
        - "*.ncb",
        - "*.sdf",
        - "*.suo",
        - "*.pdb",
        - "*.idb",
        - ".DS_Store",
        - "*.class",
        - "*.psd",
        - "*.db",
        - "*.sublime-workspace"
    folder_exclude_patterns: []
    ignored_packages:
      - "Vintage"
    font_face: Monaco
    font_size: 10
    highlight_modified_tabs: true
    hot_exit: false
    line_padding_bottom: 5
    match_brackets: true
    match_brackets_angle: true
    remember_open_files: false
    rulers:
        - 80
    show_encoding: true
    show_line_endings: true
    tab_size: 2
    translate_tabs_to_spaces: true
    trim_trailing_white_space_on_save: true
    word_wrap: true

  # Packages to be installed via PackageControl.io
  packagecontrol:
    - "Package Control"
    - "Side​Bar​Enhancements"
    - "SublimeLinter"
    - "SublimeLinter-jsl"
    - "SublimeLinter-chktex"
    - "SublimeLinter-json"
    - "SublimeLinter-javac"
    - "SublimeLinter-xmllint"
    - "SublimeLinter-contrib-sqlint"
    - "SublimeLinter-contrib-bashate"
    - "SublimeLinter-contrib-nginx-lint"
    - "SublimeLinter-contrib-ansible-lint"
    - "SublimeLinter-contrib-sublime-syntax"
    - "AnsibleSnippets"
    - "Remote​Subl"
    - "Theme - Soda"
    - "git"
    - "Material Theme"
    - "Terminal"
    - "Markdown​Editing"
    - "FileDiffs"
    - "Dockerfile Syntax Highlighting"
    - "Docker Based Build Systems"
    - "HTML-CSS-JS Prettify"
    - "LaTeXTools"
    - "LiveReload"
    - "markupsafe"
    - "Pretty JSON"
    - "Pretty YAML"
    - "python-jinja2"
    - "python-markdown"
    - "pyyaml"
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_sublime:
          license: ""
          preferences:
            theme: 'Soda Dark.sublime-theme'
            color_scheme: "ackages/Material Theme/schemes/Material-Theme.tmTheme"
            default_encoding: UTF-8
            default_line_ending: unix
            detect_indentation: false
            ensure_newline_at_eof_on_save: true
            file_exclude_patterns:
                - ".DS_Store"
                - "Desktop.ini"
                - "*.pyc"
                - "._*"
                - "Thumbs.db"
                - ".Spotlight-V100"
                - ".Trashes"
                - "*.aux",
                - "*.fls",
                - "*.idx",
                - "*.out",
                - "*.fdb_latexmk",
                - "*.pyc",
                - "*.pyo",
                - "*.exe",
                - "*.dll",
                - "*.obj",
                - "*.o",
                - "*.a",
                - "*.lib",
                - "*.so",
                - "*.dylib",
                - "*.ncb",
                - "*.sdf",
                - "*.suo",
                - "*.pdb",
                - "*.idb",
                - ".DS_Store",
                - "*.class",
                - "*.psd",
                - "*.db",
                - "*.sublime-workspace"
            folder_exclude_patterns: []
            ignored_packages:
              - "Vintage"
            font_face: Monaco
            font_size: 10
            highlight_modified_tabs: true
            hot_exit: false
            line_padding_bottom: 5
            match_brackets: true
            match_brackets_angle: true
            remember_open_files: false
            rulers:
                - 80
            show_encoding: true
            show_line_endings: true
            tab_size: 2
            translate_tabs_to_spaces: true
            trim_trailing_white_space_on_save: true
            word_wrap: true
          packagecontrol:
            - "Package Control"
            - "Side​Bar​Enhancements"
            - "git"
      roles:
        - { role: feffi.macos-sublime }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-sublime,
            macos_sublime: {
              license: "",
              preferences: {
                theme: 'Soda Dark.sublime-theme',
                color_scheme: "ackages/Material Theme/schemes/Material-Theme.tmTheme",
                default_encoding: UTF-8,
                default_line_ending: unix,
                detect_indentation: false,
                ensure_newline_at_eof_on_save: true,
                file_exclude_patterns: [
                  ".DS_Store", "Desktop.ini", "*.pyc", "._*", "Thumbs.db", ".Spotlight-V100", ".Trashes", "*.aux",
                  "*.fls", "*.idx", "*.out", "*.fdb_latexmk", "*.pyc", "*.pyo", "*.exe", "*.dll", "*.obj", "*.o",
                  "*.a", "*.lib", "*.so", "*.dylib", "*.ncb", "*.sdf", "*.suo", "*.pdb", "*.idb", ".DS_Store",
                  "*.class", "*.psd", "*.db", "*.sublime-workspace"
                ],
                folder_exclude_patterns: [],
                ignored_packages: [
                  "Vintage"
                ],
                font_face: Monaco,
                font_size: 10,
                highlight_modified_tabs: true,
                hot_exit: false,
                line_padding_bottom: 5,
                match_brackets: true,
                match_brackets_angle: true,
                remember_open_files: false,
                rulers: [
                  80
                ],
                show_encoding: true,
                show_line_endings: true,
                tab_size: 2,
                translate_tabs_to_spaces: true,
                trim_trailing_white_space_on_save: true,
                word_wrap: true
              },
              packagecontrol: [
                "Package Control",
                "Side​Bar​Enhancements"
                "git"
              ]
            }
          }
```
