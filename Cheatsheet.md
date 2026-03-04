Turn column of words into valid array

### input data: 

```
content
male
dude
man
guy
lad
boy
boyfriend
mate
bro
men
males
guys
lads
boys
```
### Stacked

* regex: ((?\<!\n)^(\w+)$)|(^(\w+)(?!\n))$|(\w+)/gm
* substitution: ${1:+["$1":"$+"}${3:+]:,}
* result:

```
["content",
"male",
"dude",
"man",
"guy",
"lad",
"boy",
"boyfriend",
"mate",
"bro",
"men",
"males",
"guys",
"lads",
"boys"]
```

### Flat
* regex: (((?\<!\n)^(\w+)$)|(^(\w+)(?!\n))$|(\w+))\n?
* substitution: ${2:+["$2":"$+"}${4:+]:,}

```["content","male","dude","man","guy","lad","boy","boyfriend","mate","bro","men","males","guys","lads","boys"]```
