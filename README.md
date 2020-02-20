# node-iptc

This module is based on the node-iptc: https://github.com/derekbaron/node-iptc but I added the support for encoding and typescript typing

This module extracts IPTC information from JPEG files. 
IPTC is (mostly non-technical) structured metadata about the image with fields like creator/artist, copyright, keywords, category, etc.  
For more information, see: http://www.adobe.com/devnet-apps/photoshop/fileformatashtml/#50577409_38034

## Installation

Installing using npm:

    npm install @vip30/node-iptc
    
## Example

```javascript
  var iptc = require('@vip30/node-iptc')
  
  fs.readFile("myImage.jpeg", function(err, data) {
      if (err) { throw err }
      var iptc_data = iptc(data);
    });
```

### For different encoding
```javascript
  var iptc = require('@vip30/node-iptc')
  
  fs.readFile("myImage.jpeg", function(err, data) {
      if (err) { throw err }
      var iptc_data = iptc(data, {
        encoding: 'Big5' // default is utf-8
      });
    });
```

Sample output
```
{
   "by_line": [
     "Ralf Roletschek"
   ],
   "date_created": "20111119",
   "time_created": "195544+0000",
   "copyright_notice": "(C) Ralf Roletschek",
   "date_time": "2011-12-19T19:55:44.000Z"
 }
```