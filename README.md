# About
ACAutomation Python Package


# Install
    pip install ACAutomation

# Usage


    >>> from ACAutomation import ACAutomation
    >>> a = ACAutomation()
    >>> a.insert('11')
    >>> a.insert('22')
    >>> a.insert('33')
    >>> a.build()
    >>> a.matchOne('0011222333')
    (2, '11')
    >>> a.matchOne('00')
    (-1, None)
    >>> a.matchAll('0011222333')
    [(2, '11'), (4, '22'), (5, '22'), (7, '33'), (7, '33'), (8, '33'), (8, '33')]


If you want to insert unicode string, please encode them to string first.

	>>> from ACAutomation import ACAutomation
	>>> a = ACAutomation()
	>>> a.insert('你好')
	>>> a.insert('你坏')
	>>> a.insert('你')
	>>> a.build()
	>>> a.matchOne('你好你坏你')
	(0, '\xe4\xbd\xa0'd)
	>>> a.matchAll('你好你坏你不存在')
	[(0, '\xe4\xbd\xa0'), (0, '\xe4\xbd\xa0\xe5\xa5\xbd'), (6, '\xe4\xbd\xa0'), (6, '\xe4\xbd\xa0\xe5\x9d\x8f'), (12, '\xe4\xbd\xa0')]
	>>> a.matchAll('不存在')
	[]
	>>> a.insert('不存在')
	>>> a.build()
	>>> a.matchAll('不存在')
	[(0, '\xe4\xb8\x8d\xe5\xad\x98\xe5\x9c\xa8')]


Once you insert a new word to ACAutomation, please remember call build method. You can call build method multiple times.

