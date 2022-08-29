# Command-Line-To-Do-App
A command-line to-do app built with Python and Typer library, and tested by Typer’s CliRunner and pytest

## Quick Start
- Clone this repository remotely.
```bash
    git clone https://github.com/DanniBot/Command-Line-To-Do-App.git
```
- Change Directory
```bash
    cd .\Command-Line-To-Do-App\
```
- Create a virtualenv and enter into it
```bash
    virtualenv name
    source name/bin/activate
```
- Install the dependencies
```bash
    pip install -r requirements.txt
```

## Features and Usages

* Show current version info
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo -v
kiratodo v0.1.0
```

* Show the global help message
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo --help
Usage: kiratodo [OPTIONS] COMMAND [ARGS]...

Options:
  -v, --version         Show the application's version and exit.
  --install-completion  Install completion for the current shell.
  --show-completion     Show completion for the current shell, to copy it or
                        customize the installation.

  --help                Show this message and exit.

Commands:
  add       Add a new to-do with a DESCRIPTION.
  clear     Remove all to-dos.
  complete  Complete a to-do by setting it as done using its TODO_ID.
  init      Initialize the to-do database.
  list      List all to-dos.
  remove    Remove a to-do using its TODO_ID.
```

* Initialize the to-do database
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo init  
to-do database location? [/Users/stephanie/.stephanie_todo.json]: 
The to-do database is /Users/stephanie/.stephanie_todo.json
```

* Add a new to-do 
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo add Do leetcodes -p 1
to-do: "Do leetcodes." was added with priority: 1
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo add Workout 30mins -p 2
to-do: "Workout 30mins." was added with priority: 2
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo add Grocery shopping -p 2 
to-do: "Grocery shopping." was added with priority: 2
```

* List all to-dos.
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo list                     

to-do list:

ID.  | Priority  | Done  | Description  
----------------------------------------
1    | (1)       | False | Do leetcodes.
2    | (2)       | False | Workout 30mins.
3    | (2)       | False | Grocery shopping.
----------------------------------------
```

* Complete a to-do by setting it as done using its TODO_ID
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo complete 2
to-do # 2 "Workout 30mins." completed!
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo list      

to-do list:

ID.  | Priority  | Done  | Description  
----------------------------------------
1    | (1)       | False | Do leetcodes.
2    | (2)       | True  | Workout 30mins.
3    | (2)       | False | Grocery shopping.
----------------------------------------
```

* Remove a to-do using its TODO_ID
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo remove 3  
Delete to-do # 3: Grocery shopping.? [y/N]: y
to-do # 3: 'Grocery shopping.' was removed
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo list      

to-do list:

ID.  | Priority  | Done  | Description  
----------------------------------------
1    | (1)       | False | Do leetcodes.
2    | (2)       | True  | Workout 30mins.
----------------------------------------
```

* Remove all to-dos
```shell
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo clear   
Delete all to-dos? [y/N]: y
All to-dos were removed
(CLI) stephanie@Dannis-MBP Command-Line-To-Do-App % python -m kiratodo list 
There are no tasks in the to-do list yet
```












