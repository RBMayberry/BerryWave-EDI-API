# JSONata Integration

BerryWave provides support for JSON transformation using **JSONata**,  
a lightweight and expressive query and transformation language for JSON data.

The API exposes endpoints that allow JSONata expressions to be applied in two primary scenarios:

1. **EDI → JSON → JSONata → JSON response**  
   An incoming EDI document is converted to BerryWave’s internal JSON representation and immediately transformed using a registered JSONata query.

2. **JSON → JSONata → JSON response**  
   Arbitrary JSON (unrelated to EDI) is transformed using a registered JSONata query.

The second use case is fully functional in the free Playground version included with this project, as well as in licensed deployments.

For readability, all endpoints in this document omit the base path `http://host:port/berrywave/v1/`

---

# EDI Transformation via JSONata

In a standard EDI-to-JSON conversion, the endpoint is:
```code
POST /transformFromEdi
```

To apply a JSONata transformation in the same request, use:
```code
POST /transformFromEdi/jsonata?query=<query-name>
```
Where:

- `<query-name>` is the name of a previously registered JSONata query.
- The request body contains the EDI payload.
- The response body contains the evaluated JSONata result.

### Example

Assume a JSONata query named:
`interchangeControlNumber` 
with the following JSONata expression:

```
{
    "isaControlNumber": interchanges.ISA_13_InterchangeControlNumber
}
```
A request to
```
POST /transformFromEdi/jsonata?query=interchangeControlNumber
```

returns a response similar to:
```
{
    "isaControlNumber": "000000001"
}
```


## Registering JSONata queries
Named JSONata queries can be registered in two ways.

### Dynamic registration
You can POST your query in a request body to
```
/jsonata/queries/{query-name}
```
For example,
```
/jsonata/queries/interchangeControlNumber
```
### Registered at startup
You may also create a file `jsonata-directory/interchangeControlNumber.jsonata`
under the application home directory and your query will be automatically registered when the application starts.

### Listing registered queries
A GET request to 
```
/jsonata/queries
```
returns a JSON array of registered query names.

## JSON transformation via JSONata

As a value-added feature included in the free API Playground,
the BerryWave API also supports general-purpose JSON transformation via JSONata.

Assuming that `myQuery` was registered as described above,
you can POST your JSON in a request body to
```
/jsonata/transformJson?query=myQuery
```
and receive the transformed JSON in the response body.