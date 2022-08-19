# Shell Scripting

## `sed`

* `sed` stands for `streamlined editor`.
* Basically, `sed` is a command-line editor, but it retains the original content unless the user saves the result using shell direction.
* Frequent usage is following:

```bash
sed 's/before/after/g' file.txt  # replace every occurrance of 'before' span into 'after'

sed -n '1p' file.txt  # print the first line only
sed -n '8,$p' file.txt  # print every line from 8th to the end of file.

sed -n '/some-word/p' file.txt  # print every line which contains the span 'some-word'
```
