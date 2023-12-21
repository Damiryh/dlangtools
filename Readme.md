# langtools
### Lex

Usage of CharIterator:
```python
from langtools.lex import CharIterator

src = "Hello, world!"
it = CharIterator(src)

while not it.end():
  if it.check(str.isspace):
    it.skip(str.isspace)
  elif it.check(str.isalnum):
    print(it.location(), 'word:', it.consume(str.isalnum))
  elif it.check(',!'):
    print(it.location(), 'symbol', it.next())
```

Output:
```
(1, 1) word: Hello
(1, 6) symbol ,
(1, 8) word: world
(1, 13) symbol !
```
