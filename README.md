<p align="center"><img src="images/gatling.png" width="40%" alt="gatling Logo" /></p>

# Gatling

NeoLoad plugin for Gatling

## Overview

This integration is a NeoLoad plugin to be installed in the [Gatling](https://gatling.io/) environment.
It allows sending live data from the Gatling test result execution to [Tricentis NeoLoad](https://www.tricentis.com/products/performance-testing-neoload/).

| Property                       | Value                                                     |
|--------------------------------|-----------------------------------------------------------|
| Maturity                       | Experimental                                              |
| Author                         | Tricentis                                                 |
| License                        | [TODO](LICENSE)                                           |
| NeoLoad Web supported versions | SaaS platform, and onPremise from version 3.2             |
| Gatling tested versions        | Version 3.9.0                                             |
| Download releases              | See the [latest release](https://github.com/Neotys-Labs/Gatling/releases/latest) |

## Installation

1. Download [Gatling](https://gatling.io/) and install in a selected directory (we'll call it ``GATLING_DIR``).
2. Download [latest release](https://github.com/Neotys-Labs/Gatling/releases/latest) of Gatling Neoload plugin (jar + scripts).
3. Create a new directory called ``plugins`` in ``GATLING_DIR``.
4. Copy ``gatling.bat`` (Windows) or ``gatling.sh`` (Linux) script in ``GATLING_DIR/bin`` directory
5. Follow steps in Configuration section.

## Configuration

Open ``GATLING_DIR/conf/gatling.conf`` file and add "neoload" to the data writers:

```yaml
  data {
    writers = [console, file, neoload]
    ...
    neoload {
      url = "https://neoload-rest.saas.neotys.com"
      token = "<your-nlw-token>"
      workspace = "<your-workspace-id>"
      testId = "<your-test-id>"
    }
  }

 
```

* url: Set the URL of the API endpoint for the NeoLoadWeb on premise deployment.
* token: User API token to authenticate to NeoLoadWeb
* workspace: The ID of the workspace to send the results to.
* testId: The ID of the test to send the results to. Not required, if not present an orphan test result will be generated. 

## Usage

Once the Gatling test starts, a new test is created in NeoLoadWeb, as seen in the "Running Tests" section of the Home page:
<img src="images/test_starting.png" width="100%" alt="Test starting" />

## Errors

| Code                           | Description                               |
|--------------------------------|-------------------------------------------|
| GATLING-ILLEGAL-ARGUMENT       | An argument is not right or not supported |
| GATLING-UNKNOWN-HOST           | The host is unknown                       |
| GATLING-SSL-HANDSHAKE          | Ssl Handshake error                       |

## NeoLoad Web Analysis

### Test Result Overview

The Overview tab presents all basic details of the Gatling test.
<img src="images/overview.png" width="100%" alt="Overview" />

More information in the [NeoLoad documentation](https://documentation.tricentis.com/neoload/nlweb/en/WebHelp/#27510.htm).

### Test Result Values

The Values tab allows sorting elements of a test quickly (Transactions and Requests).
<img src="images/values.png" width="100%" alt="Values" />

More information in the [NeoLoad documentation](https://documentation.tricentis.com/neoload/nlweb/en/WebHelp/#24271.htm).

### Test Result Events

The Events tab displays all events occurred during the Gatling test.
<img src="images/events.png" width="100%" alt="Events" />

More information in the [NeoLoad documentation](https://documentation.tricentis.com/neoload/nlweb/en/WebHelp/#24274.htm).

### Dashboards

The Dashboards view enables you to visualize in a very flexible layout how values evolve over Gatling test duration.
<img src="images/dashboards.png" width="100%" alt="Dashboards" />

More information in the [NeoLoad documentation](https://documentation.tricentis.com/neoload/nlweb/en/WebHelp/#23448.htm).

### Trends

The Trends view makes it possible to visualize and analyze the results of a selected number of tests.
<img src="images/trends.png" width="100%" alt="Trends" />

More information in the [NeoLoad documentation](https://documentation.tricentis.com/neoload/nlweb/en/WebHelp/#26401.htm).

## Troubleshooting

TODO

## ChangeLog

TODO