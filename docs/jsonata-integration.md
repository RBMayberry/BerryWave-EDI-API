# JSONata Integration

BerryWave provides support for JSON transformation using **JSONata**,
a lightweight and expressive query and transformation language for JSON data.

The API includes entry points for two use cases:
- EDI is converted to JSON, and in the same API request that JSON is then transformed
  using a JSONata query and returned as the JSON response.
- JSON -- unrelated to EDI -- is transformed
  using a JSONata query and returned as the JSON response.
  This feature is fully functional in the free Playground version provided with this project
  as well as with a licensed version.

---

## EDI transformation via JSONata

We will use a basic example to illustrate the use of a JSONata query for EDI transformation.
In this dcoument, we will omit the `http://host:port/berrywave/v1/` prefix on the URLs.

Instead of
```
/transformFromEdi
```
used for typical EDI to JSON conversions,
we will use

```
/transformFromEdi/jsonata?query=<query-name>
```
where <query-name> is the name of a JSONata query that you have previously defined.

For example, a JSONata query named `interchangeControlNumber` that extracts the interchange control number
from an X12 interchange looks like

```
{
    "isaControlNumber": interchanges.ISA_13_InterchangeControlNumber
}
```
and when used in
```
/transformFromEdi/jsonata?query=interchangeControlNumber
```

results in returned JSON like this:
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