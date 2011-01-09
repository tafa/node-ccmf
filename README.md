
## Status: pre-alpha

A library for generating or using [coord-to-coord mapping files](https://gist.github.com/769845).


## Installing / Developing

<pre>
cd node-ccmf; npm link
</pre>

## Creating CCMF files
<pre>
CCMF = require('CCMF');

CCMF.write_ccmf(stream, info, linemaps, fileinfos, mappings)
CCMF.ccmf_string(stream, info, linemaps, fileinfos, mappings)
</pre>

CCMFH-style file info lines will be created iff any fileinfo in fileinfos has any properties.

(<code>[{...}]\n</code> instead of <code>[]\n</code>)


## Using CCMF files

<pre>
ccmf = CCMF.fromStream(x, callback)
ccmf = CCMF.from{String,Buffer}(x)

ccmf.lookup(line, col)
    Result:
        null or
        {
            # You'll get as many of these fields and subfields as possible.
            line: 
            col: 
            label: 
            file: {
                sha1: 
                name: 
                path: 
                url: 
            }
        }
</pre>


