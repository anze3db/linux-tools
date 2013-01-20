Useful little linux tools
=========================

grepr
-----

    export GREP_OPTIONS='--color=auto'
    grep -rnC ${2:-3} "$1" *

It's a simple `grep` wrapper that forces the grep utility to become recursive by default. The first parameter to grepr is the phrase you're searching for, while the optional second parameter specifies the number of lines above and below the search term to be shown. 

rmr
---

    find . -name $1 | xargs rm
    
`rmr` is similar to grepr. It makes the rm utility recursive. It's useful when you have a bunch of files that end up with .orig in multiple subfolders. You would just write rmr *.orig to delete them all.


sedre
-----
   
    sed "s/$1/$2/g" $3
   
Sedre replaces all of the occurances of the first paramtere with the second parameter in the file specified by the third parameter.


seddl
----

    sed "$1d" $2
    
Seddl removes a line from a file. You would write `sed 4 myfile` to remove the fourth line from myfile.

screenshots
----------

    while true; do scrot "%Y-%m-%d_%H-%M_$2.png" & sleep $1; done

Takes a screenshot every few seconds and saves them in a file specified by the second parameter.
