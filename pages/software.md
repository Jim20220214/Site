# DOCUMENTATION 

[Home][Home]

### Code/Text Editor

#### Sublime Command Line Interface [ref][ref]

Sublime Text includes a command line tool, subl, to work with files on the command line. This can be used to open files and projects in Sublime Text, as well working as an EDITOR for unix tools, such as git and subversion.

###### [Setup](#setup) {#nav_setup}
###### [Usage](#usage) {#nav_usage}
###### [Configuring as EDITOR](#configuring-as-editor) {#nav_configuring-as-editor}

##### Setup
Some operating systems and installation methods will require a configuration change to make subl available on the PATH.

`echo 'export PATH="/Applications/Sublime Text.app/Contents/SharedSupport/bin:$PATH"' >> ~/.zprofile`

##### Usage
To see the available flags, run subl --help. The available flags will vary per operating system – the following example is from Linux:
```
Sublime Text build 4131

Usage: subl [arguments] [files]         Edit the given files
   or: subl [arguments] [directories]   Open the given directories
   or: subl [arguments] -- [files]      Edit files that may start with '-'
   or: subl [arguments] -               Edit stdin
   or: subl [arguments] - >out          Edit stdin and write the edit to stdout

Arguments:
  --project <project>:    Load the given project
  --command <command>:    Run the given command
  -n or --new-window:     Open a new window
  --launch-or-new-window: Only open a new window if the application is open
  -a or --add:            Add folders to the current window
  -w or --wait:           Wait for the files to be closed before returning
  -b or --background:     Don't activate the application
  --safe-mode:            Launch using a sandboxed (clean) environment
  -h or --help:           Show help (this message) and exit
  -v or --version:        Show version and exit

Filenames may be given a :line or :line:column suffix to open at a specific
location.
```

##### CONFIGURING AS EDITOR
To use Sublime Text as the editor for many commands that prompt for input, set your EDITOR environment variable:  
`export EDITOR='subl -w'`
>Specifying -w will cause the subl command to not exit until the file is closed.

-----
[ref]: https://www.sublimetext.com/docs/command_line.html
[Home]: https://jim20220214.github.io/Site/

