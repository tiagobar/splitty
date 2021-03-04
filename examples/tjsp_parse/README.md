# Example using ghost script

## How to extract text:

```
gs -sDEVICE=txtwrite -dFirstPage=3321 -dLastPage=3388 -o caderno3.txt caderno3-Judicial-1ªInstancia-Capital.pdf
```

Removing boilerplate

```bash
sed 's/Disponibilização:\ssexta-feira,.*//' caderno3.txt | sed 's/Publicação\sOficial\sdo\sTribunal.*//'> caderno3_parsed.txt
```

run

```
python examples/tjsp_parse/example.py
```

Check result:

```bash
cat caderno3.json
```

## Files:

caderno3-Judicial-1ªInstancia-Capital.pdf: PDF to be extracted
caderno3.txt: raw text result from ghost script
caderno3_parsed.txt: boilerplate removed with sed expresion
caderno3.json: Result using splitty script
example.py: Example script using Splitty
