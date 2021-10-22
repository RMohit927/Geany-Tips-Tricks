# Geany-Tips-Tricks

### 1. snippets.conf
```cpp
#~ # Geany's snippets configuration file
#~ #
#~ # use \n or %newline% for a new line (it will be replaced by the used EOL char(s) - LF, CR/LF, CR).
#~ # use \t or %ws% for an indentation step, it will be replaced according to the current document's indent mode.
#~ # use \s to force whitespace at beginning or end of a value ('key= value' won't work, use 'key=\svalue').
#~ # use %key% for all keys defined in the [Special] section.
#~ # use %cursor% to define where the cursor should be placed after completion. You can define multiple
#~ #     %cursor% wildcards and use the "Move cursor in snippet" to jump to the next defined cursor
#~ #     position in the completed snippet.
#~ # You can define a section for each supported filetype to overwrite default settings, the section
#~ # name must match exactly the internal filetype name, run 'geany --ft-names' for a full list.
#~ #
#~ # Additionally, you can use most of the template wildcards like {developer}, {command:...},
#~ # or {date} in the snippets.
#~ # See the documentation for details.

#~ # For a list of available filetype names, execute:
#~ # geany --ft-names

#~ # Default is used for all filetypes and keys can be overwritten by [filetype] sections
[Default]
cpp=#include<bits/stdc++.h>\nusing namespace std;\n\n#define fastio ios_base::sync_with_stdio(false); cin.tie(NULL)\n#define endl "\\n"\n#define f_input freopen("inputs/input.txt", "r", stdin)\n#define f_output freopen("inputs/output.txt", "w", stdout)\n\ntypedef long long int ll;\ntypedef long double ld;\ntypedef pair<int, int> pi;\ntypedef pair<ll, ll> pli;\ntypedef pair<ld, ld> pld;\n\ntypedef vector<int> VI;\ntypedef vector<ll> VLLI;\ntypedef vector<pi> VPI;\ntypedef vector<pli> VPLI;\n\n#define mk make_pair\n#define pb push_back\n#define test int t; cin >> t; while(t--)\n\nclass Solution{\n\tpublic void Helper(){\n\n\t}\n};\n\nint main(){\n\tfastio;\n#ifndef ONLINE_JUDGE\n\tf_input;\n\tf_output;\n#endif\n\t\n\tSolution obj;\n\n\ttest{\n\t\tobj.Helper();\n\t}\n\n\treturn 0;\n}


#~ # special keys to be used in other snippets, cannot be used "standalone"
#~ # can be used by %key%, e.g. %brace_open%
#~ # nesting of special keys is not supported (e.g. brace_open=\n{\n%brace_close% won't work)
#~ # key "wordchars" is very special, it defines the word delimiting characters when looking for
#~ # a word to auto complete, leave commented to use the default wordchars
#~ [Special]
#~ brace_open=\n{\n\t
#~ brace_close=}\n
#~ block=\n{\n\t%cursor%\n}
#~ block_cursor=\n{\n\t%cursor%\n}
#~ #wordchars=_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789

#~ # Optional keybindings to insert snippets
#~ # Note: these can be overridden by Geany's configurable keybindings
#~ [Keybindings]
#~ #for=<Ctrl>7

#~ [C]
#~ if=if (%cursor%)%block_cursor%
#~ else=else%block_cursor%
#~ for=for (i = 0; i < %cursor%; i++)%block_cursor%
#~ while=while (%cursor%)%block_cursor%
#~ do=do\n{\n\t%cursor%\n} while (%cursor%)\n
#~ switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%

[C++]
if=if (%cursor%)%block_cursor%
else=else%block_cursor%
for=for (int i = 0; i < %cursor%; i++)%brace_open%\n%brace_close%
while=while (%cursor%)%block_cursor%
do=do\n{\n\t%cursor%\n} while (%cursor%)\n
switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
try=try%block%\ncatch (%cursor%)%block_cursor%
b ={\n\t%cursor%\n}
#~ b={\n\t%cursor%\n}

#~ [Java]
#~ if=if (%cursor%)%block_cursor%
#~ else=else%block_cursor%
#~ for=for (int i = 0; i < %cursor%; i++)%brace_open%\n%brace_close%
#~ while=while (%cursor%)%block_cursor%
#~ do=do\n{\n\t%cursor%\n} while (%cursor%)\n
#~ switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
#~ try=try%block%\ncatch (%cursor%)%block_cursor%

#~ [PHP]
#~ if=if (%cursor%)%block_cursor%
#~ else=else%block_cursor%
#~ for=for ($i = 0; $i < %cursor%; $i++)%brace_open%\n%brace_close%
#~ while=while (%cursor%)%block_cursor%
#~ do=do\n{\n\t%cursor%\n} while (%cursor%)\n
#~ switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
#~ try=try%block%\ncatch (%cursor%)%block_cursor%

#~ [Javascript]
#~ if=if (%cursor%)%block_cursor%
#~ else=else%block_cursor%
#~ for=for (i = 0; i < %cursor%; i++)%block_cursor%
#~ while=while (%cursor%)%block_cursor%
#~ do=do\n{\n\t%cursor%\n} while (%cursor%)\n
#~ switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
#~ try=try%block%\ncatch (%cursor%)%block_cursor%

#~ [C#]
#~ if=if (%cursor%)%block_cursor%
#~ else=else%block_cursor%
#~ for=for (i = 0; i < %cursor%; i++)%block_cursor%
#~ while=while (%cursor%)%block_cursor%
#~ do=do\n{\n\t%cursor%\n} while (%cursor%)\n
#~ switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
#~ try=try%block%\ncatch (%cursor%)%block_cursor%

#~ [Vala]
#~ if=if (%cursor%)%block_cursor%
#~ else=else%block_cursor%
#~ for=for (i = 0; i < %cursor%; i++)%block_cursor%
#~ while=while (%cursor%)%block_cursor%
#~ do=do\n{\n\t%cursor%\n} while (%cursor%)\n
#~ switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
#~ try=try%block%\ncatch (%cursor%)%block_cursor%

#~ [ActionScript]
#~ if=if (%cursor%)%block_cursor%
#~ else=else%block_cursor%
#~ for=for (i = 0; i < %cursor%; i++)%block_cursor%
#~ while=while (%cursor%)%block_cursor%
#~ do=do\n{\n\t%cursor%\n} while (%cursor%)\n
#~ switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
#~ try=try%block%\ncatch (%cursor%)%block_cursor%

#~ [Python]
#~ for=for i in xrange(%cursor%):\n\t
#~ if=if %cursor%:\n\t
#~ elif=elif %cursor%:\n\t
#~ else=else:\n\t
#~ while=while %cursor%:\n\t
#~ try=try:\n\t%cursor%\nexcept Exception, ex:\n\t
#~ with=with %cursor%:\n\t
#~ def=def %cursor% (%cursor%):\n\t""" Function doc """\n\t
#~ class=class %cursor%:\n\t""" Class doc """\n\t\n\tdef __init__ (self):\n\t\t""" Class initialiser """\n\t\tpass

#~ [Ferite]
#~ iferr=iferr%block_cursor%fix%block%
#~ monitor=monitor%block_cursor%handle%block%

#~ [Haskell]

#~ [HTML]
#~ table=<table>\n\t<tr>\n\t\t<td>%cursor%</td>\n\t</tr>\n</table>

#~ [Erlang]
#~ case=case %cursor% of\n\t%cursor% -> %cursor%\nend
#~ if=if\n\t%cursor% -> %cursor%\nend
#~ begin=begin\n\t%cursor%\nend
#~ fun=fun(%cursor%) ->\n\t%cursor%\nend
#~ try=try %cursor% of\n\t%cursor% ->\n\t%cursor%\ncatch\n\t%cursor% ->\n\t%cursor%\nend
#~ module=-module(%cursor%).
#~ export=-export(%cursor%).
#~ compile=-compile(%cursor%).
#~ include=-include(%cursor%).
```

### 2. Set Build Commands
Compile:
``` 
g++ -Wall -c "%f"
```
Build:
```
g++ -Wall -o "%p/exe/%e" "%f"
```
