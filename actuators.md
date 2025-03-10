# When hunting for exposed Spring Boot Actuator endpoints, use a comprehensive wordlist that covers default paths, legacy endpoints, and alternative locations. The list below is structured for use with tools like ffuf, gobuster, feroxbuster. It includes common Actuator endpoints (e.g. health checks, metrics), less obvious paths (legacy endpoints from Spring Boot 1.x, integration endpoints), and alternate base paths (in case the management context path is changed).


# Default Actuator Base Path
actuator
actuator/

# Common Actuator Endpoints (Spring Boot 2.x/3.x)
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
actuator/httpexchanges
actuator/quartz
actuator/sbom

# Legacy Spring Boot 1.x Endpoints (No "/actuator" Prefix by Default)
health
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

# Spring Cloud & Extended Actuator Endpoints
actuator/gateway
actuator/gateway/routes        # Spring Cloud Gateway - RCE possible in older versions (CVE-2022-22947)
actuator/refresh               # Spring Cloud Config Refresh - Reloads config (may expose secrets)
actuator/restart               # Spring Cloud Context Restart - Could be used for denial of service
actuator/jolokia               # JMX via Jolokia (Possible RCE with misconfigurations)
actuator/hawtio                # Hawtio JMX Management Console (Exploitable if misconfigured)
actuator/hawtio/index.html

# Miscellaneous Actuator Endpoints
actuator/httpexchanges         # HTTP Request Traces (Info Disclosure)
actuator/conditions            # Auto-Configuration Report (Can reveal app internals)
actuator/flyway                # Database Migrations via Flyway (Info Disclosure)
actuator/liquibase             # Database Migrations via Liquibase (Info Disclosure)
actuator/integrationgraph      # Spring Integration Graph (Information Leak)
actuator/heapdump              # Dumps JVM Heap Memory (Critical if exposed - may contain secrets)
actuator/loggers               # Adjust Logging Levels (Info Leak, may enable debug logs)
actuator/metrics               # Application Metrics (May expose internal system details)
actuator/auditevents           # Security Audit Logs (Can reveal login attempts & access control)



# Alternative Base Paths for Actuator Endpoints

management
management/
management/health
management/info
management/env
management/metrics
management/configprops
management/beans
management/loggers

manage
manage/
manage/health
manage/info

admin
admin/
admin/health
admin/env

monitoring
monitoring/
monitoring/health
monitoring/info
monitoring/env

internal
internal/
internal/health
internal/info
internal/env
