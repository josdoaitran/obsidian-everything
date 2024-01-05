# obsidian-everything
Everything notes and collections about Obsidian

# Plugins collection
- Templater
- Sync-Remote
- multi-column-markdown
https://github.com/ckRobinson/multi-column-markdown
- excalidraw
https://forum.obsidian.md/t/excalidraw-full-featured-sketching-plugin-in-obsidian/17367/1

# Template collections

## Table of Content
https://github.com/SilentVoid13/Templater/discussions/888
- Version 1
```
>[!SUMMARY] Table of Contents
<%*
    let headers = await tp.file.content
        .split('\n') // split file into lines
        .filter(t => t.match(/^[#]+\s+/gi)) // only get headers
        .map(h => {
            let header_level = h.split(' ')[0].match(/#/g).length;
             // get header text without special characters like '[' and ']'
            let header_text = h.substring(h.indexOf(' ') + 1).replace(/[\[\]]+/g, '');
            let header_link = `[[${tp.file.title}#${header_text}|${header_text}]]`

            // prepend block-quote (>), indentation and bullet-point (-)
            return `>${'    '.repeat(header_level - 1) + '- ' + header_link}`;
        })
        .join('\n')
%><% headers %>
```
- Version 2
```
## Table of Contents
<%*
    let headers = await tp.file.content
        .split('\n') // split file into lines
        .filter(t => t.match(/^[#]+\s+/gi)) // only get headers
        .map(h => {
            let header_level = h.split(' ')[0].match(/#/g).length;
             // get header text without special characters like '[' and ']'
            let header_text = h.substring(h.indexOf(' ') + 1).replace(/[\[\]]+/g, '');
            let header_link = `[[${tp.file.title}#${header_text}|${header_text}]]`

            // add indentation and bullet-point
	    return `${'    '.repeat(header_level - 1) + '- ' + header_link}`;
        })
        .join('\n')
%><% headers %>
```

# Collumn Template
- 
https://github.com/efemkay/obsidian-modular-css-layout
