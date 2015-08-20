# py3_imap_utf7

Python3 encoding and decoding utilities for the IMAP modified UTF-7 encoding. See [RFC2152](https://tools.ietf.org/html/rfc2152)

This is a direct port from the python 2 version from [Mailpile](https://github.com/mailpile/Mailpile/blob/master/mailpile/mail_source/imap_utf7.py)

#

This version works better than the one found in [imapclient](https://bitbucket.org/mjs0/imapclient/src/ea03d8a7265a6a4164474422e2d749b68db40e65/imapclient/imap_utf7.py?at=default), which fails to do roundtrip encoding in some situations like:

```python
from imap_utf7 import encode, decode

s = 'foo\r\n\nbar\n'
assert s == decode(encode(s))
```

Although control characters are usually rejected by IMAP servers.

*I will add some unittests when I find the time, finish the porting properly and maybe switch to an in-memory implementations for better performance*
