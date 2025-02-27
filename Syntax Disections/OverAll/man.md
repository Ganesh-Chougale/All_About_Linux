## **`man`**:  
`man` → mans commands gives manual to following file, command, syntax or function.  
```bash
man passwd
```  
will show all the manual regarding `passwd` command  
press `spacebar` to pagedown  
press `q` (quit) to exit from manaual command  

### other navigations  

| Key | Function |
|------|----------|
| `Up` / `Down` | Scroll up/down one line at a time |
| `Page Up` / `Page Down` | Scroll up/down one full screen |
| `Home` | Jump to the beginning of the manual |
| `End` | Jump to the end of the manual |
| `/pattern` | Search for a specific pattern (case-sensitive) |
| `n` | Jump to the next search match |
| `N` | Jump to the previous search match |
| `h` | Open the help screen with navigation instructions |
| `q` | Quit the `man` page |
| `g` | Go to the beginning of the document |
| `G` | Go to the end of the document |
| `d` | Scroll half a page down |
| `u` | Scroll half a page up |
| `space` | Scroll one page down |
| `b` | Scroll one page up |

### Reading man page (common heading structure)  

| **Heading** | **Description** |
|------------|----------------|
| **NAME** | The name of the command and a brief description. |
| **SYNOPSIS** | The syntax of the command, including available options. |
| **DESCRIPTION** | A detailed explanation of what the command does. |
| **OPTIONS** | A list of available options (flags) and their effects. |
| **EXIT STATUS** | The possible exit codes returned by the command. |
| **EXAMPLES** | Practical usage examples of the command. |
| **FILES** | Lists configuration or system files related to the command. |
| **SEE ALSO** | References to related commands or documentation. |
| **BUGS** | Known issues or limitations of the command. |
| **AUTHOR** | The creator(s) of the command. |
| **COPYRIGHT** | Licensing and copyright information. |
| **HISTORY** | Historical background or changes over different versions. |

You can navigate these sections using search (`/heading`) or by scrolling manually inside `man`.


`pinfo` is asthetic version of `man`  