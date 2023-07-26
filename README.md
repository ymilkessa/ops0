# An Open Protocol for Streaming

This is a proposal for a "more flexible" market for monetized audio content on the internet, such as music and podcasts. This includes a public protocol for Digital Rights Management.

## Components

1. Hosting servers
   - Servers that host content for artists.
2. Client applications
   - Apps that listeners use in their music consumption.
3. Local Records Module (LRM)
   - A software component inside of user devices.

### Local Records Module

This is a tool that all users who consume content (via this protocol) need to have on their devices as a prerequisite. This could be an operating system package or any other form of open source program that can act as an interface to a device's audio output.

The key function of the LRM is to locally record which programs used a device's audio output, when they used it and for how long. Old records can be erased after some duration (see verification window below). When a web browser uses the speaker, the LRM should also record what site it was. By default, all such records should be labelled as "UNTRACKED."

For instance, a single record could look like this in a json format:

```
{
   "program_identifier_1": "Google Chrome",
   "program_identifier_2": "youtube.com",             // If on a browser, include the website
   "track_identifier": "lofi hip hop radio ...",
   "start_time": "1690349370",                        // in unix timestamp in seconds
   "end_time": "1690349490",
   "type": "UNTRACKED",                               // untracked item; subsequent fields are left empty
   "host_server_pubkey": "",
   "unique_track_id": "",
   "random_string": "",
   "host_signature": ""
}
```

#### TODO: More description needed here

## Definitions

`hk`: The public key a hosting server.

`ck`: Public key of a client application.
