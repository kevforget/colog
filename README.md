# COLOG : Python log colorizer
Colog is a python log colorizer inspired by Chalk from the Node JS world

## Usage
```python
import colog

print(colog.green("This is green"))
```

Colog is also compatible with the python logging library mostly to not write unicode chars into files.

```python
import logging
import colog

logger = logging.getLogger('test app')

fh = logging.FileHandler('test.log')
fh.setFormatter(colog.NoColorLoggingFormatter('%(levelname)s | %(message)s'))

ch = logging.StreamHandler()
ch.setFormatter(logging.Formatter(colog.red('%(levelname)s')+' | %(message)s'))

logger.addHandler(fh)
logger.addHandler(ch)

logger.warning("This is a "+colog.yellow('WARNING'))
```

## Licensing
COLOG is an Apache 2.0 Licensed open-source project.