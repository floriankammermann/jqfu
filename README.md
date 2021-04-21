# valuable jq commands

## get all available json path
`jq '[path(..)|map(if type=="number" then "[]" else tostring end)|join(".")|split(".[]")|join("[]")]|unique|map("."+.)|.[]'`

## select from an array on nested values
`| jq '.DATA[]  | select(.DOMAIN == "domain2") | .DOMAINID'`
