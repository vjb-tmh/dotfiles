
--------- Auto Complete (.vimrc) ----------
```
inoremap <tab> <c-r>=InsertTabWrapper()<cr>

function! InsertTabWrapper()
    let col = col('.') - 1
    if !col || getline('.')[col - 1] !~ '\k'
        return "\<tab>"
    else
        return "\<c-p>"
    endif
endfunction
```

--------- Build Skeletons (.vimrc) ---------
```
au BufNewFile *.py 0r ~/.vim/py.skel | let IndentStyle = "python"
```

--------- Python Skeleton (place in ~/.vim )---------
```
#!/usr/bin/python
"""
Python script skeleton.
"""
import sys
import argparse

def main():
    # ------ Parse arguments ------- #
    '''
    parser = argparse.ArgumentParser(description=__doc__)

    parser.add_argument('first_arg')
    parser.add_argument('--three', nargs=3)
    parser.add_argument('--optional', nargs='?')
    parser.add_argument('--all', nargs='*', dest='all')
    parser.add_argument('--one-or-more', nargs='+')

    args = parser.parse_args()

    print(args)
    print(args.first_arg)
    '''
    # ------------------------------ #
    print('Start your code here.')

if __name__ == "__main__":
    sys.exit(main())
```

--------- color scheme (.vimrc) ---------
```
set background=dark
set t_Co=256
let g:colors_name = "duoduo"

highlight Normal guisp=#292929 guifg=#f2f2f2 guibg=#292929 gui=NONE ctermfg=255 ctermbg=235 cterm=NONE

highlight IncSearch guifg=#000000 guibg=#90ee90 gui=NONE ctermfg=16 ctermbg=120 cterm=NONE
highlight WildMenu guisp=#ffff45 guifg=#000000 guibg=#ffff45 gui=NONE ctermfg=16 ctermbg=227 cterm=NONE
highlight SignColumn guisp=#363636 guifg=NONE guibg=#363636 gui=NONE ctermbg=237 cterm=NONE
highlight SpecialComment guisp=NONE guifg=#ffa500 guibg=NONE gui=NONE ctermfg=214 cterm=NONE
highlight Typedef guisp=NONE guifg=#deb887 guibg=NONE gui=bold ctermfg=180 cterm=bold
highlight Title guisp=NONE guifg=#ffbfe5 guibg=NONE gui=NONE ctermfg=218 cterm=NONE
highlight Folded guisp=#383838 guifg=#999999 guibg=#383838 gui=NONE ctermfg=247 ctermbg=237 cterm=NONE
highlight PreCondit guisp=NONE guifg=#acace6 guibg=NONE gui=bold ctermfg=147 cterm=bold
highlight Include guisp=NONE guifg=#acace6 guibg=NONE gui=NONE ctermfg=147 cterm=NONE
highlight Float guisp=NONE guifg=#ff477e guibg=NONE gui=bold ctermfg=204 cterm=bold
highlight StatusLineNC guisp=#4d4d4d guifg=#87cfeb guibg=#4d4d4d gui=NONE ctermfg=117 ctermbg=239 cterm=NONE
highlight NonText guisp=#292929 guifg=#4d4d4d guibg=#292929 gui=NONE ctermfg=239 ctermbg=235 cterm=NONE
highlight DiffText guisp=#fa2d2d guifg=NONE guibg=#fa2d2d gui=NONE ctermbg=196 cterm=NONE
highlight ErrorMsg guisp=#fa2d2d guifg=#ffffff guibg=#fa2d2d gui=NONE ctermfg=231 ctermbg=196 cterm=NONE
highlight Ignore guisp=NONE guifg=#292929 guibg=NONE gui=NONE ctermfg=235 cterm=NONE
highlight Debug guisp=NONE guifg=#ffa500 guibg=NONE gui=NONE ctermfg=214 cterm=NONE
highlight PMenuSbar guisp=#585858 guifg=#000000 guibg=#585858 gui=NONE ctermfg=16 ctermbg=240 cterm=NONE
highlight Identifier guisp=NONE guifg=#98fb98 guibg=NONE gui=NONE ctermfg=120 cterm=NONE
highlight SpecialChar guisp=NONE guifg=#ffa500 guibg=NONE gui=NONE ctermfg=214 cterm=NONE
highlight Conditional guisp=NONE guifg=#f5f55d guibg=NONE gui=bold ctermfg=227 cterm=bold
highlight StorageClass guisp=NONE guifg=#deb887 guibg=NONE gui=bold ctermfg=180 cterm=bold
highlight Todo guisp=#ffff17 guifg=#0000ff guibg=#ffff17 gui=NONE ctermfg=21 ctermbg=226 cterm=NONE
highlight Special guisp=NONE guifg=#ffa500 guibg=NONE gui=NONE ctermfg=214 cterm=NONE
highlight LineNr guisp=#2e2e2e guifg=#9b9c9a guibg=#2e2e2e gui=NONE ctermfg=249 ctermbg=236 cterm=NONE
highlight StatusLine guisp=#4d4d4d guifg=#87ceeb guibg=#4d4d4d gui=NONE ctermfg=117 ctermbg=239 cterm=NONE
highlight Label guisp=NONE guifg=#f5f55d guibg=NONE gui=NONE ctermfg=227 cterm=NONE
highlight PMenuSel guisp=#a0cf63 guifg=#000000 guibg=#a0cf63 gui=NONE ctermfg=16 ctermbg=149 cterm=NONE
highlight Search guisp=#ffff45 guifg=#000000 guibg=#ffff45 gui=NONE ctermfg=16 ctermbg=227 cterm=NONE
highlight Delimiter guisp=NONE guifg=#ffa500 guibg=NONE gui=NONE ctermfg=214 cterm=NONE
highlight Statement guisp=NONE guifg=#f5f55d guibg=NONE gui=bold ctermfg=227 cterm=bold
highlight Comment guisp=NONE guifg=#7cbdd6 guibg=NONE gui=NONE ctermfg=74 cterm=NONE
highlight Character guisp=NONE guifg=#ffa0a0 guibg=NONE gui=NONE ctermfg=217 cterm=NONE
highlight Number guisp=NONE guifg=#ff477e guibg=NONE gui=bold ctermfg=204 cterm=bold
highlight Boolean guisp=NONE guifg=#ffa0a0 guibg=NONE gui=NONE ctermfg=217 cterm=NONE
highlight Operator guisp=NONE guifg=#d7d700 guibg=NONE gui=NONE ctermfg=184 cterm=NONE
highlight CursorLine guisp=#454545 guifg=NONE guibg=#454545 gui=NONE ctermbg=238 cterm=NONE
highlight Question guisp=NONE guifg=#50de50 guibg=NONE gui=bold ctermfg=77 cterm=bold
highlight WarningMsg guisp=NONE guifg=#fc9292 guibg=NONE gui=bold ctermfg=210 cterm=bold
highlight VisualNOS guisp=NONE guifg=NONE guibg=NONE gui=bold,underline cterm=bold,underline
highlight DiffDelete guisp=#e0ffff guifg=#0000ff guibg=#e0ffff gui=bold ctermfg=21 ctermbg=195 cterm=bold
highlight ModeMsg guisp=NONE guifg=#dbdbdb guibg=NONE gui=bold ctermfg=253 cterm=bold
highlight CursorColumn guisp=#454545 guifg=NONE guibg=#454545 gui=NONE ctermbg=238 cterm=NONE
highlight Define guisp=NONE guifg=#acace6 guibg=NONE gui=NONE ctermfg=147 cterm=NONE
highlight Function guisp=NONE guifg=#98fb98 guibg=NONE gui=NONE ctermfg=120 cterm=NONE
highlight FoldColumn guisp=#3d3d3d guifg=#87ceeb guibg=#3d3d3d gui=NONE ctermfg=117 ctermbg=238 cterm=NONE
highlight PreProc guisp=NONE guifg=#acace6 guibg=NONE gui=bold ctermfg=147 cterm=bold
highlight Visual guisp=#474747 guifg=NONE guibg=#474747 gui=NONE ctermbg=239 cterm=NONE
highlight MoreMsg guisp=NONE guifg=#2e8b57 guibg=NONE gui=bold ctermfg=29 cterm=bold
highlight VertSplit guisp=#4d4d4d guifg=#87ceeb guibg=#4d4d4d gui=NONE ctermfg=117 ctermbg=239 cterm=NONE
highlight Exception guisp=NONE guifg=#f5f55d guibg=NONE gui=bold ctermfg=227 cterm=bold
highlight Keyword guisp=NONE guifg=#deb887 guibg=NONE gui=bold ctermfg=180 cterm=bold
highlight Type guisp=NONE guifg=#a8e332 guibg=NONE gui=bold ctermfg=148 cterm=bold
highlight DiffChange guisp=#d600d6 guifg=NONE guibg=#d600d6 gui=NONE ctermbg=164 cterm=NONE
highlight Cursor guisp=#00ff00 guifg=#000000 guibg=#00ff00 gui=NONE ctermfg=16 ctermbg=46 cterm=NONE
highlight Error guisp=#fa2d2d guifg=#ffffff guibg=#fa2d2d gui=NONE ctermfg=231 ctermbg=196 cterm=NONE
highlight PMenu guisp=#404040 guifg=#eeeeee guibg=#404040 gui=NONE ctermfg=255 ctermbg=237 cterm=NONE
highlight SpecialKey guisp=NONE guifg=#292929 guibg=NONE gui=NONE ctermfg=235 cterm=NONE
highlight Constant guisp=NONE guifg=#ffa0a0 guibg=NONE gui=NONE ctermfg=217 cterm=NONE
highlight Tag guisp=NONE guifg=#ffa500 guibg=NONE gui=NONE ctermfg=214 cterm=NONE
highlight String guisp=NONE guifg=#ed8aa9 guibg=NONE gui=NONE ctermfg=211 cterm=NONE
highlight PMenuThumb guisp=#a8a8a8 guifg=#b2b2b2 guibg=#a8a8a8 gui=NONE ctermfg=249 ctermbg=248 cterm=NONE
highlight MatchParen guisp=#008b8b guifg=NONE guibg=#008b8b gui=NONE ctermbg=30 cterm=NONE
highlight Repeat guisp=NONE guifg=#f5f55d guibg=NONE gui=bold ctermfg=227 cterm=bold
highlight Directory guisp=NONE guifg=#c0c0fc guibg=NONE gui=NONE ctermfg=147 cterm=NONE
highlight Structure guisp=NONE guifg=#deb887 guibg=NONE gui=bold ctermfg=180 cterm=bold
highlight Macro guisp=NONE guifg=#d7d787 guibg=NONE gui=NONE ctermfg=186 cterm=NONE
highlight DiffAdd guisp=#2c72ab guifg=NONE guibg=#2c72ab gui=NONE ctermbg=25 cterm=NONE
highlight Conceal guisp=NONE guifg=#4d4d4d guibg=NONE gui=NONE ctermfg=239 cterm=NONE
highlight lCursor guifg=#000000 guibg=#00ffff guisp=#00ffff gui=NONE ctermfg=NONE ctermbg=14 cterm=NONE
highlight ColorColumn guisp=#9c4343 guifg=NONE guibg=#9c4343 gui=NONE ctermbg=131 cterm=NONE
highlight CursorLineNr guisp=NONE guifg=#90ee90 guibg=NONE gui=NONE ctermfg=120 cterm=NONE
```

-------- .minttyrc ---------
```
BellType=0
BoldAsFont=yes
FontHeight=12
AllowBlinking=yes
CursorType=block
Transparency=low
Rows=25
Term=xterm-256color
Font=Consolas
Scrollbar=none
ScrollMod=shift
Columns=80
OpaqueWhenFocused=yes
ThemeFile=
Locale=en_US
Charset=UTF-8

BackgroundColour=26,26,26
ForegroundColour=211,208,200
CursorColour=211,208,200
Black=51,51,51
BoldBlack=102,102,102
Red=242,119,122
BoldRed=242,119,122
Green=153,204,153
BoldGreen=153,204,153
Yellow=235,189,91
BoldYellow=235,189,91
Blue=102,153,204
BoldBlue=102,204,204
Magenta=242,119,122
BoldMagenta=242,119,122
Cyan=102,204,204
BoldCyan=102,204,204
White=211,208,200
BoldWhite=211,208,200

Font=Courier New
```
