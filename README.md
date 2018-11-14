# Quickstart

```
docker-compose up -d
# or internally
dev up -d
```

# Editor Config

## neovim

```vim
Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
Plug 'junegunn/fzf.vim'
Plug 'w0rp/ale'

call ale#Set('ruby_lsp_address', '127.0.0.1:7658')
call ale#linter#Define('ruby', {
\   'name': 'lsp',
\   'lsp': 'socket',
\   'language': 'ruby',
\   'address_callback': ale#VarFunc('ruby_lsp_address'),
\   'project_root_callback': 'ale#ruby#FindProjectRoot'
\})

call ale#Set('elixir_lsp_address', '127.0.0.1:7659')
call ale#linter#Define('elixir', {
\   'name': 'lsp',
\   'lsp': 'socket',
\   'language': 'elixir',
\   'address_callback': ale#VarFunc('elixir_lsp_address'),
\   'project_root_callback': 'ale#handlers#elixir#FindMixUmbrellaRoot'
\})

call ale#Set('elm_lsp_address', '127.0.0.1:7660')
call ale#linter#Define('elm', {
\   'name': 'lsp',
\   'lsp': 'socket',
\   'language': 'elm',
\   'address_callback': ale#VarFunc('elm_lsp_address'),
\   'project_root_callback': 'ale_linters#sh#language_server#GetProjectRoot'
\})

call ale#Set('bash_lsp_address', '127.0.0.1:7661')
call ale#linter#Define('sh', {
\   'name': 'lsp',
\   'lsp': 'socket',
\   'language': 'sh',
\   'address_callback': ale#VarFunc('bash_lsp_address'),
\   'project_root_callback': 'ale_linters#sh#language_server#GetProjectRoot'
\})

let g:ale_linters = {
\ 'ruby': ['lsp'],
\ 'elixir': ['lsp'],
\ 'elm': ['lsp'],
\ 'sh': ['lsp'],
\}

let g:ale_fixers = {
\ 'elixir': ['mix_format']
\}
let g:ale_fix_on_save = 1

let g:ale_ruby_lsp_address = 'default:7658'
let g:ale_elixir_lsp_address = 'default:7659'
let g:ale_elm_lsp_address = 'default:7660'
let g:ale_bash_lsp_address = 'default:7661'
```

## VS Code
