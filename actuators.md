# When hunting for exposed Spring Boot Actuator endpoints, use a comprehensive wordlist that covers default paths, legacy endpoints, and alternative locations. The list below is structured for use with tools like ffuf, gobuster, feroxbuster. It includes common Actuator endpoints (e.g. health checks, metrics), less obvious paths (legacy endpoints from Spring Boot 1.x, integration endpoints), and alternate base paths (in case the management context path is changed).

# Default Actuator base path and discovery
actuator
actuator/

# Common Actuator endpoints (Spring Boot 2.x/3.x and above)
actuator/health
actuator/info
actuator/env
actuator/metrics
actuator/loggers
actuator/threaddump
actuator/heapdump
actuator/logfile
actuator/configprops
actuator/beans
actuator/mappings
actuator/scheduledtasks
actuator/caches
actuator/conditions
actuator/auditevents
actuator/sessions
actuator/shutdown
actuator/startup
actuator/prometheus

# Legacy Spring Boot 1.x endpoints (no /actuator prefix by default)
info
env
metrics
loggers
trace
dump
heapdump
logfile
beans
autoconfig
mappings
configprops
flyway
liquibase
auditevents
shutdown

# Spring Cloud and integration endpoints
actuator/gateway
actuator/gateway/routes  # (for Spring Cloud Gateway) 
actuator/refresh         # (Spring Cloud Refresh Scope)
actuator/restart         # (Spring Cloud Context Restart Endpoint)
actuator/jolokia         # (JMX via Jolokia if on classpath)
actuator/hawtio          # (Hawtio console if on classpath)
actuator/hawtio/index.html

# Other possible Actuator extension endpoints (from various Spring projects or apps)
actuator/httpexchanges   # (HTTP request traces, if enabled)
actuator/conditions      # (auto-config conditions report, SB 2.x)
actuator/flyway          # (DB migrations via Flyway)
actuator/liquibase       # (DB migrations via Liquibase)
actuator/integrationgraph  # (Spring Integration graph)
actuator/heapdump         # (Heap dump – also listed above)
actuator/loggers          # (Loggers – also listed above)
actuator/metrics          # (Metrics – also listed above)
actuator/auditevents      # (Audit events – also listed above)

# Alternative management base paths (if actuator is served under a custom context)&#8203;:contentReference[oaicite:2]{index=2}&#8203;:contentReference[oaicite:3]{index=3}
management/health
management/info
management/env
management/metrics
management/configprops
management/beans
management/loggers
manage/health
manage/info
admin/health
admin/env
