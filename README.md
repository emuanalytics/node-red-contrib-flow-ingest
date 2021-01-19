# Flo.w Real-Time Ingest for Node-RED

This package provides a Node-RED stomp out node for ingesting data to [Flo.w Real-Time](https://developer.emu-analytics.net/docs/flow-realtime/).

The node is a specialized version of the standard Node-RED MQTT out node.

## Node Configuration

- server: Flo.w Real-Time MQTT broker configuration.
- dataset: Dataset ID to ingest to.
- action: Ingest action (insert, upsert or delete).
- QoS: Standard MQTT quality-of-service option.

Leave action or qos blank if you want to set them via msg properties.

## Server Configuration

- Server: Flo.w Real-Time broker domain name.
- Port: 1883 (non-TLS) or 8883 (TLS).
- App ID: Flo.w application ID.
- API Key: Flo.w API key (must have MQTT write permission).
- Enable TLS: Configure TLS support (use with port 8883).
- Advanced options: As standard MQTT configuration.

## Message Format

- `msg.payload` - the data to ingest. (A data object or array of data objects).

Optionally, you can specify ingest action and qos via msg (node configuration has priority):

- `msg.action` - Ingest action.
- `msg.qos` - MQTT QoS.