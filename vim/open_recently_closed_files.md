# vim - open recently closed files

:bro ol

:bro[wse] ol[dfiles][!]
                        List file names as with |:oldfiles|, and then prompt
                        for a number.  When the number is valid that file from
                        the list is edited.
                        If you get the |press-enter| prompt you can press "q"
                        and still get the prompt to enter a file number.
                        Use ! to abandon a modified buffer. |abandon|
                        {not when compiled with tiny or small features}
                        
https://stackoverflow.com/a/29688194

## cheat it

cht.sh vim open recent file
curl cheat.sh/vim+open=recent=file
