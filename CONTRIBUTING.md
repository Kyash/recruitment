# Contributing

## Issue

Issueテンプレートに沿って自由に起票してください。  
内容によっては対応せずクローズすることもあります。

## Pull Request

文字の揺らぎやかなの開きを統一するために、TextLintをCIで走らせています。  
[Atom](https://atom.io)、[VSCode](https://code.visualstudio.com)、[vim](https://www.vim.org/)を使うと、下記のプラグインを入れることでリアルタイムで校正を行えます。

- Atom: [linter-textlint](https://atom.io/packages/linter-textlint), [linter-markdownlint](https://atom.io/packages/linter-markdownlint)
- VSCode: [vscode-textlint](https://marketplace.visualstudio.com/items?itemName=taichi.vscode-textlint), [vscode-markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- Vim: [ale](https://github.com/dense-analysis/ale), [lightline.vim](https://github.com/itchyny/lightline.vim), [lightline-ale](https://github.com/maximbaz/lightline-ale)

<details>
  <summary>vimのlightlineとaleに関する設定はこちら</summary>

```
let g:lightline = {}
let g:lightline.component_expand = {
    \  'linter_checking': 'lightline#ale#checking',
    \  'linter_warnings': 'lightline#ale#warnings',
    \  'linter_errors': 'lightline#ale#errors',
    \  'linter_ok': 'lightline#ale#ok'
    \ }
let g:lightline.component_type = {
    \   'linter_checking': 'left',
    \   'linter_warnings': 'warning',
    \   'linter_errors': 'error',
    \   'linter_ok': 'left'
    \ }
let g:lightline.active = { 'right': [[ 'linter_checking', 'linter_errors', 'linter_warnings', 'linter_ok'  ]]  }
let g:ale_linters = {}
let g:ale_linters.markdown = ['textlint']
let g:ale_completion_enabled = 1
```
</details>

表記揺れなどの校正ルールを追加・修正したい場合には [prh-rules/kyash-prh.yml](https://github.com/Kyash/recruitment/blob/master/prh-rules/kyash-prh.yml) を編集してください。
