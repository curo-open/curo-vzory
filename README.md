# curo-vzory

to export v browsery navstiv http://localhost:3000/api/templates/export?config=/home/daniel/Dev/xt/curo/curo-vzory/vzory-export.yml 

## how to scan all used template vars
run and open in libre office
```
grep -rni ./ -Po -e "var\.(\w+)" > /tmp/vars.csv
```


