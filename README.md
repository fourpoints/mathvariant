# Mathvariant
MathML mathvariant Unicode table

## Preview
[Github.io HTML preview](https://htmlpreview.github.io/?https://github.com/fourpoints/mathvariant/blob/master/index.html)


## Code example
Note: JSON does not support integer keys, so we can't store the result of maketrans as a JSON file.

```py
import json
from pathlib import Path

def load(path):
    return json.loads(path.read_text(encoding="utf-8"))

def maketrans(fonts):
    return {
        font_name: str.maketrans(alphabet)
        for font_name, alphabet in fonts.items()
    }

mathvariant = maketrans(load(Path("mathvariant.json")))

# Example use
print("ABC".translate(mathvariant["italic"]))
print(mathvariant["italic"][ord("A")])
``` 
