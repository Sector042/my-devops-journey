Level	Command	                                         What it does
5 → 6	find . -type f -size 1033c	                 Find files by size and type
6 → 7	find / -user X -group Y 2>/dev/null	         Search whole filesystem, hide errors
7 → 8	grep word file	                                 Search inside a file for text
8 → 9	sort file | uniq -u	                         Find unique lines using a pipe
9 → 10	strings file | grep =	                         Extract text from binary, filter it
