---
name: Upstream Timeout
publisher: Kong Inc.
categories:
  - traffic-control
type: plugin

desc: Set timeouts on routes and override service-level timeouts
description: |
  Use the Upstream Timeout plugin to configure route-specific timeouts.
  This plugin overrides any service-level timeout settings.

kong_version_compatibility:
  enterprise_edition:
    compatible: true

cloud: true
enterprise: true
plus: false

params:
  name: upstream-timeout
  service_id: false
  consumer_id: false
  route_id: true
  protocols:
    - name: http
    - name: https
  dbless_compatible: yes
  config:
    - name: connect_timeout
      required: false
      default: null
      value_in_examples: 4000
      datatype: integer
      description: |
        The timeout, in milliseconds, for establishing a connection to the upstream server.
        Overrides the service object [`connect_timeout`](/gateway/latest/how-kong-works/routing-traffic/#proxying-and-upstream-timeouts) setting, if the setting exists.
    - name: send_timeout
      required: false
      default: null
      value_in_examples: 5000
      datatype: integer
      description: |
        The timeout, in milliseconds, between two
        successive write operations when sending a request to the upstream server.
        Overrides the service object [`write_timeout`](/gateway/latest/how-kong-works/routing-traffic/#proxying-and-upstream-timeouts) setting, if the setting exists.
    - name: read_timeout
      required: false
      default: null
      value_in_examples: 5000
      datatype: integer
      description: |
        The timeout, in milliseconds, between two
        successive read operations when receiving a response from the upstream server.
        Overrides the service object [`read_timeout`](/gateway/latest/how-kong-works/routing-traffic/#proxying-and-upstream-timeouts) setting, if the setting exists.
---
