# Using WebViewer as a Data Parser

Demo of a simple data parser that takes JSON input from FileMaker, parses/processes the data in some way, and then returns that data to FileMaker.

## Webviewer Code
```
<html>
<head>
<script>
function advancedWordCount(string) {
    var words = string.replace(/[.]/g, '').split(/\s/);
    var freqMap = {};
    words.forEach(function(w) {
        if (!freqMap[w]) {
            freqMap[w] = 0;
        }
        freqMap[w] += 1;
    });
    FileMaker.PerformScriptWithOption("Return Data",freqMap,4);
    return freqMap;
}
</script>
</head>
<body>
Parser is Loaded.
</body>
</html>
```