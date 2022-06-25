# mathvariant
MathML mathvariant Unicode table

## Preview
[Github.io HTML preview](https://htmlpreview.github.io/?https://github.com/fourpoints/mathvariant/blob/master/index.html)


## Code example
Note: JSON does not support integer keys, so we can't store the result of maketrans as a JSON file.

```py
def maketrans(fonts):
    return {
        font_name: str.maketrans(alphabet)
        for font_name, alphabet in fonts.items()
    }

mathvariant = maketrans(json.loads(Path("mathvariant.json").read_text(encoding="utf-8"))

# Example use
print("ABC".translate(mathvariant["italic"]))
print(mathvariant["italic"][ord("A")])
``` 
