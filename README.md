### pylama
---
https://github.com/klen/pylama

```py
from pylama.lint import Linter as BaseLinter

class Linter(BaseLinter):
  
  def allow(self, path):
    return 'wow' in path
    
  def run(self, path, **meta):
    with open(path) as f:
      if 'wow' in f.read():
        return [{
          lnum: 0,
          col: 0,
          text: 'Wow has been finded,',
          type: 'WOW'
        }]

my_redefined_options = {
  'linters': ['pip257', 'pydocstyle', 'pycodestyle', 'pyflakes' ...],
  'ignore': ['D203', 'D213', 'D406', 'D407', 'D413', ...],
  'select': ['R1705' ...],
  'sort': 'F,E,W,C,D,...',
  'skip': '*__init__.py,*/test/*.py,...',
  'async': True,
  'force': True
}
my_path = '...'

options = parser_options([my_path], **my_redefined_options)
errors = check_path(options, rootdir='.')
```

```sh
pip install pylama
pylama
pylama -i W,E501
pylama -l "pycodestyle,mccabe"
pylama --linters=gjslint --ignore=E:0010 <path_to_directory_or_file>
```

```
```


