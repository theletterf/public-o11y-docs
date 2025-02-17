(couchbase)=

# Couchbase server

<meta name="description" content="Use this Splunk Observability Cloud integration for the Couchbase monitor. See benefits, install, configuration, and metrics">

The {ref}`Splunk Distribution of OpenTelemetry Collector <otel-intro>` uses the {ref}`Smart Agent receiver <smartagent-receiver>` with the Couchbase server monitor type to collect metrics from Couchbase servers.

This integration is only available on Kubernetes and Linux.

## Benefits

```{include} /_includes/benefits.md
```

## Installation

```{include} /_includes/collector-installation-linux.md
```

## Configuration

```{include} /_includes/configuration.md
```

### Example

To activate this integration, add the following to your Collector configuration:

```
receivers:
  smartagent/couchbase:
    type: collectd/couchbase
    ...  # Additional config
```

Next, add the monitor to the `service > pipelines > metrics > receivers` section of your configuration file:

```
service:
 pipelines:
   metrics:
     receivers: [smartagent/couchbase]
```

## Metrics

The following metrics are available for this integration:

<div class="metrics-yaml" url="https://raw.githubusercontent.com/signalfx/signalfx-agent/main/pkg/monitors/collectd/couchbase/metadata.yaml"></div>

### Notes

```{include} /_includes/metric-defs.md
```

## Troubleshooting

```{include} /_includes/troubleshooting.md
```
