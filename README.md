# ubergraph-viz
Example workflow for rendering SPARQL query results from Ubergraph using obographviz

## Requirements
You will need the following tools on your `PATH` (or use the docker script, see below):

- `og2dot`—https://github.com/cmungall/obographviz
- `dot`—https://graphviz.org
- `jq`—https://stedolan.github.io/jq/
- `curl`
- `make`

## Queries

Add SPARQL queries to the `sparql` folder, using file extension `.rq`. 
Each query should be a SELECT query which projects these variables: `?s`, `?slabel`, `?p`, `?plabel`, `?o`, `?olabel`.

## Running

Run a `make` target based on the name of the SPARQL query to run, replacing `.rq` with `.pdf`, e.g.: `make two-hop-neighborhood.pdf`.

<img src="../../raw/master/examples/two-hop-neighborhood.png" width="400">

### Running via docker
If you have docker on your system, all the needed tools are available in the docker image accessed via the `run.sh` script

```
./run.sh make two-hop-neighborhood.pdf
```

## Styling

Change the styling by editing [ubergraph-style.json](../../blob/master/style/ubergraph-style.json). 
Color names are defined here: https://graphviz.org/doc/info/colors.html.
