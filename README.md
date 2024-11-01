# KBV and ePA Medication Profile Comparison

## Overview
This document provides a summary of the differences between the KBV E-Rezept profiles and the ePA Medication profile, as identified by the compare.py script. Additionally, a remark field is generated and adjusted to give advice for the mapping process.


## Hosted Results
The results of the comparison can be viewed directly through these hosted links:
- [Mapping: PatientEuLab|0.2.0-ci in KBV_PR_MIO_LAB_Patient|1.0.0-kommentierung.2](https://hwaldmller.github.io/structure_comparer-main/projects/labreport/docs/PatientEuLab%7C0.2.0-ci_to_KBV_PR_MIO_LAB_Patient%7C1.0.0-kommentierung.2.html)

## Web-App

This project provides a web app to configure the mapping between different profiles for different projects.

### Backend

Start the backend service from the repository root

```bash
python server.py --project-dir projects/<name>
```

The started service is available at `localhost:5000`. The OpenAPI specification is available with the route `/spec`.

#### REST Client

The service can be evaluated through a predefined collection of requests located in `rest/requests.http`. This collection utilizes the [Rest Client](`https://marketplace.visualstudio.com/items?itemName=humao.rest-client`) extension for easy execution.

The target `host` for these requests is specified in the devcontainer.json file under the rest-client.environmentVariables setting, as shown below:

```json
"rest-client.environmentVariables": {
    "local": {
        "host": "localhost:5000"
    }
}
```

To execute a request, simply click on the Send Request link located above the respective request definition in the requests.http file. This action triggers the request to the configured host, facilitating the testing process directly within your development environment.

### Frontend

Frontend is currently moved to a seperate Repo: https://github.com/SvenSommer/structure_comparer_frontend

#### Features

- **Mappings Visualization**: Visualize mappings between FHIR profiles with detailed views for each mapping, including properties, classifications, and remarks.

- **Edit and Configure Mappings**: Directly edit mappings to adjust classifications, add remarks, and configure mappings as per project requirements.

- **Responsive Design**: The frontend is designed to be responsive, providing a seamless experience across various devices and screen sizes.

#### Building for Production

To build the frontend for production, run the following command:
    ```bash
    ng build --prod
    ```
This will create a `dist/` directory with optimized files ready to be deployed to a production server.

For more information on Angular development, visit [Angular's official documentation](https://angular.io/docs).
