# `https://facebook.tracking.exposed`

The implementation of Tracking Exposed for Facebook.

## Scripts

### `scripts/fetch-impressions-to-stream.js`

This script fetches impressions from the legacy fbtrex API and ingests them into the new processor based setup. This script is meant to run as a recurring process every minute. For the script to work, supply a `TREX_LEGACY_API_PASSWORD` environment variable. This can be done using `dotenv` and editing the `.env` file in the project root.
