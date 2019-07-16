# [collection-utils](https://github.com/jackd/collection-utils)

python utilities for working with collections

## Installation

```bash
git clone https://github.com/jackd/collection-utils
cd collection-utils
pip install -e .
```

## Usage

```python
from collection_utils.sequence import Sequence
from collection_utils.mapping import Mapping

def loud_square(x):
    value = x**2
    print('(%s)**2 = %s' % (x, value))
    return value

squares = Sequence.mapped(range(5), loud_square)
print('Array access gives value %s' % squares[3])
# (3)**2 = 9
# Array access gives value 9
print(len(squares))
# 5

base_dict = {'x': 4, 'y': -10}
squared_dict = Mapping.mapped(base_dict, loud_square)
for k in ('x', 'y'):
    print('squared_dict["%s"] value is %s' % (k, squared_dict[k]))
# (4)**2 = 16
# squared_dict["x"] value is 16
# (-10)**2 = 100
# squared_dict["y"] value is 100
```

See [tests](tests) for more

## Running tests

```bash
python -m pytest .
```
