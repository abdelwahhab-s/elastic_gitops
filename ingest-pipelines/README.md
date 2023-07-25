To avoid Json Parsing issues like : `Unexpected character ('"' (code 34)): was expecting comma to separate OBJECT entries`, follow the below instructions:

1. Create your pipeline in Kibana Dev Tools
2. Copy the pipeline from Dev Tools as a `cURL` command
3. Create a separate file for the pipeline or edit an existing one
4. Paste the pipeline body from the cURL command
5. Fix any Json parsing and escape issues. For example, when you copy the `cURL` command, the `''` will be escaped as in this line: `"if": "ctx.json?.checkType != '\'''\''"` You need to change it back to `"if": "ctx.json?.checkType != ''"` to avoid the Json parsing errors.
6. Commit the updates on a separate branch