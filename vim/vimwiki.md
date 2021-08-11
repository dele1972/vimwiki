# vimwiki

- Github: [vimwiki/vimwiki](https://github.com/vimwiki/vimwiki)
- YouTube: []()
  - Github: [Brodie Robertson](https://github.com/BrodieRobertson/vimwiki)
  - **start outside a buffer**: `nvim vimwiki/index.wiki`
- YouTube: [Productivity Setup with Vimwiki, Taskwarrior and MDwiki: Part 1](https://youtu.be/A1YgbAp5YRc)
  - recommend further tools
    - [Dynalon/mdwiki](https://github.com/Dynalon/mdwiki)
      1. Download the latest release [MDwiki 0.6.2](https://github.com/Dynalon/mdwiki/releases/download/0.6.2/mdwiki-0.6.2.zip) (it will never be updated anymore, but still working good)
      2. extract/copy the `mdwiki.html` to the vimwiki folder
      3. now this html file can be opened and shows the vimwiki
        - maybe the opening of other files could be supressed
        - allow local file access then
          - firefox: `about:config` --> search `unique` --> set `privacy.file_uniqye_origin` from `true` to `false`
      4. look at this [documentation](https://dynalon.github.io/mdwiki/#!index.md) for more layouting
        - this page is a wiki/md file too!
  - recommend further plugins
    - tbabe/taskwiki
      - taskwarrior integration
    - plasticboy/vim-markdown
      - easier markdown usage
  - **create wiki article with folder**: `[Dev](dev/index.md)`
  - `init.vim` configurations
    - `let g:vimwiki_list = [{'path':'~/dev/vimwiki', 'syntax': 'markdown', 'ext': '.md'}]`
      - set vimwiki folder to `/tmp/vimwiki`, change to *markdown*
    - `let g:vimwiki_ext2syntax - {'.md': 'markdown', '.markdown': 'markdown', '.mdown': 'markdown'}`
      - set various file extensions to *markdown*
    - `let g:vimwiki_markdown_link_ext = 1`
      - makes vimwiki markdown links as [text](text.md) instead of [text](text)
    - `let g:taskwiki_markup_syntax = 'markdown'`
    - `let g:markdown_folding = 1`
    
