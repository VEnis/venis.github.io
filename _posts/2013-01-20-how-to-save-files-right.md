---
category: "Source Control"
---

1. Create temporary file. Handle all possible exceptions.
2. Write data to that temporary file. Handle all possible exceptions.
3. Close temporary file. During that exceptions are also possible.
4. If all previous steps completes successfully, rename temporary file to existing file and handle all possible exceptions.

Steps 1-3 can be combined together if there is a function available that creates file with given content.

Following those steps prevents a lot of failures like insufficient disk space or reset during file saving.
