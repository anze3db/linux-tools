#!/usr/bin/python


# sudo ln -s /home/smotko/coding/linux-stuff/tablet-fix.py /usr/bin/tablet-fix
# sudo chmod +x /usr/bin/tablet-fix

from os import popen, system
from re import compile


ids = []
for f in popen('xinput').readlines():
    if "Genius MousePen" in f:
        p = compile(r'id=(?P<id>[0-9]*)')
        m = p.search(f)
        ids.append(m.group('id'))
        
[system('xinput set-prop %s "Coordinate Transformation Matrix" 0.5 0 0 0 0.5 0 0 0 1.0' % i) for i in ids]
[system('xinput set-prop %s "Coordinate Transformation Matrix" 1.0 0 0 0 1.0 0 0 0 1.0' % i) for i in ids]
