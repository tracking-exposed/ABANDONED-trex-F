# `https://facebook.tracking.exposed`

The implementation of Tracking Exposed for Facebook.

Place an environment file in `/home/tracking/Environment` that contains the following keys:

- TREX_LOG_DIR
- TREX_LEGACY_API_PASSWORD

## Scripts

### `scripts/fetch-impressions-to-stream.js`

This script fetches impressions from the legacy fbtrex API and ingests them into the new processor based setup. This script is meant to run as a recurring process every minute. For the script to work, supply a `TREX_LEGACY_API_PASSWORD` environment variable. This can be done using `dotenv` and editing the `.env` file in the project root.

## Systemd

### `facebook-tracking-exposed.target`

This systemd target collects all units that are require to operate the infrastructure for `facebook.tracking.exposed`.

### `fetch-impressions.service`

Run the script to connect to the legacy API to retrieve the latest impressions. This is a oneshot service.

### `fetch-impressions.timer`

Run `fetch-impressions.service` every minute.
