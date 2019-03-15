#sublime text 3 necessary keybinding that solve my problems On ubuntu 16.04 lts.

The problem was 
1) ctrl+space not showing any suggestions
2) down arrow not scrooling the autocomplete
3) up arrow not scrolling the autocomplete
4) Enter not working for autocomplete

Here is the quick fix for that . I found that in the web on difference place and merge it 

{
       "keys": ["up"],
       "command": "up_arrow_in_auto_complete",
       "context": [{
           "key": "auto_complete_visible",
           "operator": "equal",
           "operand": true
       }]
   }, {
       "keys": ["down"],
       "command": "auto_complete",
       "context": [{
           "key": "auto_complete_visible","operator": "equal",
           "operand": true
       }]
   },


   { "keys": ["ctrl+space"], "command": "auto_complete" },
   { "keys": ["ctrl+space"], "command": "replace_completion_with_auto_complete", "context":
       [
           { "key": "last_command", "operator": "equal", "operand": "insert_best_completion" },
           { "key": "auto_complete_visible", "operator": "equal", "operand": false },
           { "key": "setting.tab_completion", "operator": "equal", "operand": true }
       ]
   },
