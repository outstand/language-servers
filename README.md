# Quickstart

```
docker-compose up -d
```

# Editor Config

## neovim

```
Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
Plug 'junegunn/fzf.vim'
Plug 'autozimu/LanguageClient-neovim', {
    \ 'branch': 'next',
    \ 'do': 'bash install.sh',
    \ }

" language client setup
let g:LanguageClient_autoStart = 1
let g:LanguageClient_autoStop = 0
let g:LanguageClient_loggingFile = '/tmp/languageclient.log'
let g:LanguageClient_loggingLevel = 'WARN'
let g:LanguageClient_serverCommands = {
  \ 'ruby': ['tcp://default:7658'],
  \ }
```

## VS Code
