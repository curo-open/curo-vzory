# curo-vzory

to export v browsery navstiv 
http://localhost:3000/api/templates/export?config=/home/daniel/Dev/curo/curo-vzory/vzory-export.yml

## how to scan all used template vars
run and open in libre office
```rg
grep -rni ./ -Po -e "var\.(\w+)" > /tmp/vars.csv
```


## scan all template expressions
```bash
# unique
rg -os '\{\{\s?\?([^}])+\}\}' --json | jq 'select(.type=="match")|.data.path.text as $fn|.data.submatches[]|[$fn, .match.text]' | jq -s '.[]|.[1]' | jq -s 'sort|unique'

# per file
rg -os '\{\{\s?\?([^}])+\}\}' --json | jq 'select(.type=="match")|.data.path.text as $fn|.data.submatches[]|[$fn, .match.text]' | jq -s 'group_by(.[0])'  -r
```


export import vlastnych vzorov
http://localhost:3000/api/templates/xt-export
http://localhost:3000/api/templates/xt-import?file=/home/swift/Desktop/templates.json
http://localhost:3000/api/templates/xt-import?file=/var/lib/curo/storage/templates.json
http://localhost:3000/api/templates/xt-import?file=C:\ProgramData\curo\templates.json
- test4
