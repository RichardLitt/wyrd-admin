Here is the list of the functionality of the Wired In prototype. 

##Packages

 * `os` for printing and recieving commands from the terminal
 * `datetime` for managing timestamps and some NLP time tasks
 * `sys` for arguments terminal-side management
 * `re` for regex
 * `random` for making random values for some task assignment functions
 * `textwrap` for pretty printing (`pprint` also good)

##External Files

 * `tasks` file of stuff to do  
 * `log` file of past things done  
 * `shopping list`  

##External applications

 * `ghi`, terminal-side Github Issues manager
 * `ical`, terminal-side Mac Calendar manager

##Top-level Functions

###help
Arguments:
Optional:
Comments: prints out a 30 line helpdesk with all of the commands, their shortcuts, and the optional or mandatory values. No user input possible - just a printout. 

###begin
Arguments:
Optional:
Comments:


###end
Arguments:
Optional:
Comments:


###fence
Arguments:
Optional:
Comments:


###status
Arguments:
Optional:
Comments:


###cease
Arguments:
Optional:
Comments:


###topics
Arguments:
Optional:
Comments:


###PID
Arguments: a PID such as '345'
Optional:
Comments: shows all of the information for any manually entered PID. 

###search
Arguments:
Optional:
Comments:


###today
Arguments:
Optional:
Comments:


###yesterday
Arguments:
Optional:
Comments:


###week
Arguments:
Optional:
Comments:


###write
Arguments:
Optional:
Comments:


###projects
Arguments:
Optional:
Comments:


###todo
Arguments:
Optional:
Comments:


###random
Arguments:
Optional:
Comments:


###task
Arguments:
Optional:
Comments:


###mvim
Arguments:
Optional:
Comments:


###vim
Arguments:
Optional:
Comments:


###unify
Arguments:
Optional:
Comments:


###list
Arguments:
Optional:
Comments:


###buy
Arguments:
Optional:
Comments:


###ical
Arguments:
Optional:
Comments:


###ghi
Arguments:
Optional:
Comments:


##Hidden Functions

 * `edit` can be seen as `mvim` or `vim` - basically, it goes to the file
   used with a shorthand in the argument, and opens it in mvim or vim to
edit it. This is the basic way to edit logs, tasks, the code, or the
shopping list, due to issues with .csv printing.  
 * `print_time_labels(input_time)` basically takes a 00:00:00 format
   and prints it with hours, minutes, and seconds attached. There might
be a way to do this using `datetime` - I wasn't able to find a
satisfactory one, so I've made quite a few of these little natural
language generation functions.  
 * `time_add` is something that `datetime` can definitely do better: it
   just adds together the amount of time between two 00:00:00 stamps.  
 * `day_index` gives the index for a day in a year. Used for dealing
   with tasks that go over a month boundary. There's probably a smarter
way to do this, too.  
 * `number_string` returns a number for a natural language input. one = 1 Object orientation won't change the need for these little functions.  
 * `date_string` takes most natural language inputs and outputs it in a
   timestamp machine-readable format. 
 * `random_navi_animal` was an easter egg that was totally awesome.
   Returns the name of a random animal from Avatar.
 * `void` was a function that asks what you've been doing since your
   last task. I stopped using it as it was very annoying. 
 * `task_division` is basically the algorithm which figures out how to
   split different sorts of tasks over days, or not, or whether they are
urgent, or not. There's quite a few different types: `hard` for
non-split types, `soft` for splittable tasks, `over` for when it should
rollover over various days, `cont` for when it should happen everday,
and `x` for not urgent and it doesn't show up. Each of these has a `d-`
option, which means that it has a deadline or not, which affects how it
is split. We can do this better.  

##Manually added values

 * `exp_wpd` is the amount of minutes you predecide mean 100%
   productivity.

##Notes

 * We should probably keep a terminal-side functionality.
 * Amount of tasks completed might be just as useful as expected minutes
   to work per day. At the same time, `exp_wpd` should be fluid - for
weekends, it might be better if it was less, for instance.
