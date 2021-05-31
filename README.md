[1]: https://github.com/dice-group/RAKI-Drill-Endpoint

# Deploy

## Build the DRILL Docker image

Follow  the documentation in
[Drill][1] and name the image `drill`.

## Build the Verbalizer Docker image

Run the script: `build.sh`.
The name of the image will be `raki-verbalizer-webapp`.

# Start

Start the application by running: `docker-compose up`.

# Example request

A request has two parameters.
One with an input file (e.g., `input.json`) that contains an input for Drill as described in [Drill][1] and name the image `drill`.
and another parameter with a file (e.g., `ontology.owl`) that contains an ontology, for instance `biopax.owl`.

Request example with Curl:
```bash
ontology="@ontology.owl"
input="@input.json"
response=$0.json

curl \
	-F ontology=$ontology \
	-F input=$input \
	-H "charset=utf-8" \
	-o $response \
	http://localhost:9081/raki
```