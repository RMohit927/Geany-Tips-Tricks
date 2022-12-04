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
cpp=#include<bits/stdc++.h>\nusing namespace std;\n\n#define fastio ios_base::sync_with_stdio(false); cin.tie(NULL)\n#define endl "\\n"\n#define f_input freopen("inputs/input.txt", "r", stdin)\n#define f_output freopen("inputs/output.txt", "w", stdout)\n\ntypedef long long int ll;\ntypedef long double ld;\ntypedef pair<int, int> pi;\ntypedef pair<ll, ll> pli;\ntypedef pair<ld, ld> pld;\n\ntypedef vector<int> VI;\ntypedef vector<ll> VLLI;\ntypedef vector<pi> VPI;\ntypedef vector<pli> VPLI;\n\n#define mk make_pair\n#define pb push_back\n#define test int t; cin >> t; while(t--)\n\nclass Solution{\npublic:\n\tvoid Helper(){\n\n\t}\n};\n\nint main(){\n\tfastio;\n#ifndef ONLINE_JUDGE\n\tf_input;\n\tf_output;\n#endif\n\t\n\tSolution obj;\n\n\ttest{\n\t\tobj.Helper();\n\t}\n\n\treturn 0;\n}
cpp_basic=#include<bits/stdc++.h>\nusing namespace std;\n\n#define f_input freopen("inputs/input.txt", "r", stdin)\n#define f_output freopen("inputs/output.txt", "w", stdout)\n#define fastio ios_base::sync_with_stdio(false); cin.tie(NULL)\n#define endl "\\n"\n\nint main(){\n\tfastio;\n\n#ifndef ONLINE_JUDGE\n\tf_input;\n\t//~ f_output;\n#endif\n\n\treturn 0;\n}
grid_4=// right, top, left, bottom\nint dx[4] = {0, -1, 0, 1};\nint dy[4] = {1, 0, -1, 0};
grid_8=int dx[8] = {0, -1, -1, -1, 0, 1, 1, 1};\nint dy[8] = {1, 1, 0, -1, -1, -1, 0, 1};

# Graph
adj_list_graph=void addEdge(vector<int> adj[], int u, int v){\n\tadj[u].push_back(v);\n\tadj[v].push_back(u);\n}\n
print_graph=void print_graph(vector<int> adj[]){\n\tfor (int i = 0; i < adj.size(); i++) {\n\t\tcout << i << " = ";\n\t\tfor (int x : adj[i]){\n\t\t\tcout  << " -> " << x;\n\t\t}\n\t\tcout << endl;\n\t}\n\tcout << endl;\n}\n

# Tree
tree=struct Node{\n\tint data;\n\tNode *left, *right;\n};\n\nNode* newNode(int data){\n\tNode* temp = new Node();\n\ttemp->left = temp->right = NULL;\n\ttemp->data = data;\n\treturn temp;\n}\n
print_tree=void print_tree_inorder(TreeNode* root){\n\tif(root == NULL) return;\n\tprint_tree_inorder(root->left);\n\tcout << root->data << " ";\n\tprint_tree_inorder(root->right);\n}\n

# Linkedlist
linked_list=class List{\npublic:\n\tint data;\n\tList *next;\n\tList(){};\n\tList(int data){\n\t\tthis->data=data;\n\t\tnext = NULL;\n\t};\n};\n
print_linked_list=void print_linked_list(List *root){\n\twhile(root != NULL){\n\t\tcout << root->data;\n\t\tif(root->next) cout << " -> ";\n\t\troot = root->next;\n\t}\n\tcout << endl;\n}\n

# Vector
pb=push_back
mp=make_pair
vi=vector<int> 
vvi=vector<vector<int>> 
vpii=vector<pair<int, int>> 
vs=vector<string>
vc=vector<char>
vvc=vector<vector<char>>  
print_vi=void print_vector(vector<int> &arr){\n\tfor(int it: arr) cout << it << " ";\n\tcout << endl;\n}\n
print_vvi=void print_vector_of_vector(vector<vector<int>> &arr){\n\tfor(int i=0; i<arr.size(); i++){\n\t\tcout << i << ": ";\n\t\tfor(int no: arr[i]){\n\t\t\tcout << no << " - ";\n\t\t}\n\t\tcout << endl;\n\t}\n\tcout << endl;\n}
print_vs=void print_vector(vector<string> &arr){\n\tfor(string it: arr) cout << it << " ";\n\tcout << endl;\n}\n

# Map
mii=map<int, int>
mci=map<char, int>
msi=map<string, int>
umii=unordered_map<int, int>
umsi=unordered_map<string, int>
umci=unordered_map<char, int>

# Set
si=set<int>
usi=unordered_set<int>
usc=unordered_set<char>

# Pair
pii=pair<int, int>
pipii=pair<int, pair<int, int>>

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
for=for(int i=0; i<%cursor%; i++){\n%brace_close%
while=while (%cursor%)%block_cursor%
do=do\n{\n\t%cursor%\n} while (%cursor%)\n
switch=switch (%cursor%)%brace_open%case %cursor%:\n\t\t%cursor%\n\t\tbreak;\n\tdefault:\n\t\t%cursor%\n%brace_close%
try=try%block%\ncatch (%cursor%)%block_cursor%
b={\n\t%cursor%\n}
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

By Default:
```
g++ -Wall -o "%e" "%f"
```
Change it into:
```
g++ -Wall -o "%p/exe/%e" "%f"
```

Execute:
```
./exe/%e
```

### 3. Split string with delimeter in CPP
```
vector<string> split(string str, char delimiter) { 
		vector<string> internal; 
		stringstream ss(str); // Turn the string into a stream. 
		string tok; 

		while(getline(ss, tok, delimiter)) { 
			internal.push_back(tok); 
		} 
		return internal; 
}

// Just need to call via
vector<string> words = split(sentence, ' ');
```
