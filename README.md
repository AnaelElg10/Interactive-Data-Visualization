# GraphQL and D3.js Visualization Project

## Overview

This project combines GraphQL with D3.js to create interactive visualizations. The project is divided into two main parts: a GraphQL server and a D3.js-based frontend for visualizing data.

## Project Structure

The project is divided into two main parts:

tp8/
    graphql/
        Dockerfile
        index.js
        model.graphql
        package-lock.json
        package.json
        resolvers.js
    note_aide
    stack.yml
    tp8.md
    ui/
        bar.html
        css/
            colorbrewer.css
            style.css
            test.js
        data/
            countries.json
            departments.json
            population.csv
            population.json
            sales.bson
        france.html
        index.html
        js/
            d3.min.js
            d3.v7.min.js
        prestation_bar.html
        prestation.html

The `graphql` directory contains the GraphQL server. The `ui` directory contains the D3.js-based frontend for visualizing data.


## GraphQL Server

The GraphQL server is located in the `tp8/graphql` directory. It uses Apollo Server and MongoDB to serve data.

### Files

- **Dockerfile**: Configuration for Docker container.
- **index.js**: Entry point for the GraphQL server.
- **model.graphql**: GraphQL schema definitions.
- **package.json**: Project dependencies and scripts.
- **resolvers.js**: Resolver functions for the GraphQL queries.

### Setup

1. Navigate to the `tp8/graphql` directory.
2. Install dependencies:
    ```sh
    npm install
    ```
3. Start the server:
    ```sh
    node index.js
    ```

## Frontend

The frontend is located in the `tp8/ui` directory and uses D3.js for data visualization.

### Files

- **bar.html**: Visualization for bar charts.
- **css/**: Contains CSS files for styling.
- **data/**: Contains data files in various formats (JSON, CSV, BSON).
- **france.html**: Visualization for France map.
- **index.html**: Main entry point for the frontend.
- **js/**: Contains D3.js library files.
- **prestation_bar.html**: Visualization for prestation bar charts.
- **prestation.html**: Visualization for prestations.

### Setup

1. Open `tp8/ui/index.html` in a web browser to view the main page.
2. Navigate to other HTML files for specific visualizations.

### Example

The `france.html` file visualizes data from `data/departments.json` and a GraphQL endpoint:

```html
<script>
    var promises = [];
    promises.push(d3.json('data/departments.json'));
    promises.push(d3.json("http://127.0.0.1:4000/?query={departments{department count}}"));

    Promise.all(promises).then(function (values) {
        const geojson = values[0];
        const dpts = values[1].data.departments;
        // Visualization code here
    });
</script>
```

## Dependencies

@apollo/server : Apollo Server for GraphQL.
d3.js : JavaScript library for producing dynamic, interactive data visualizations.
mongodb : MongoDB driver for Node.js.
graphql : GraphQL library for JavaScript.

## License

This project is licensed under the ISC License. 

This [README.md](http://_vscodecontentref_/#%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22c%3A%5C%5CUsers%5C%5Celagg%5C%5CDocuments%5C%5CCours%5C%5CM1%5C%5CS7%5C%5CData%20Base%5C%5Cbdd_22007315_21910171%281%29%5C%5CREADME.md%22%2C%22_sep%22%3A1%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Felagg%2FDocuments%2FCours%2FM1%2FS7%2FData%20Base%2Fbdd_22007315_21910171%281%29%2FREADME.md%22%2C%22scheme%22%3A%22file%22%7D%7D) provides a clear and structured overview of your project, including setup instructions and descriptions of the main components.