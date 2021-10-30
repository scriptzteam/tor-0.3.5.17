# tor-0.3.5.17
```
Changes in version 0.3.5.17 - 2021-10-26
  The major change in this version is that v2 onion services are now
  disabled at the client, service, and relay: any Tor nodes running this
  version and onward will stop supporting v2 onion services. This is the
  last step in the long deprecation process of v2 onion services.
  Everyone running an earlier version, whether as a client, a relay, or
  an onion service, should upgrade to Tor 0.3.5.17, 0.4.5.11,
  or 0.4.6.8.

  o Major feature (onion service v2, backport from 0.4.5.11):
    - See https://blog.torproject.org/v2-deprecation-timeline for
      details on how to transition from v2 to v3.
    - The control port commands HSFETCH and HSPOST no longer allow
      version 2, and it is no longer possible to create a v2 service
      with ADD_ONION.
    - Tor no longer allows creating v2 services, or connecting as a
      client to a v2 service. Relays will decline to be a v2 HSDir or
      introduction point. This effectively disables onion service
      version 2 Tor-wide. Closes ticket 40476.

  o Minor features (bridge, backport from 0.4.6.8):
    - We now announce the URL to Tor's new bridge status at
      https://bridges.torproject.org/ when Tor is configured to run as a
      bridge relay. Closes ticket 30477.

  o Minor features (fallbackdir):
    - Regenerate fallback directories for October 2021. Closes
      ticket 40493.

  o Minor bugfixes (compatibility, backport from 0.4.6.8):
    - Fix compatibility with the most recent Libevent versions, which no
      longer have an evdns_set_random_bytes() function. Because this
      function has been a no-op since Libevent 2.0.4-alpha, it is safe
      for us to just stop calling it. Fixes bug 40371; bugfix
      on 0.2.1.7-alpha.
      ```
