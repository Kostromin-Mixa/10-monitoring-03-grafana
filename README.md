
- Утилизация CPU для nodeexporter (в процентах, 100-idle)

100 - ((irate(node_cpu_seconds_total{job="nodeexporter",mode="idle"}[5m])) * 100)

- CPULA 1/5/15

avg by (instance)(rate(node_cpu_seconds_total{job="nodeexporter",mode="idle"}[1m])) * 100

avg by (instance)(rate(node_cpu_seconds_total{job="nodeexporter",mode="idle"}[5m])) * 100

avg by (instance)(rate(node_cpu_seconds_total{job="nodeexporter",mode="idle"}[15m])) * 100

- Количество свободной оперативной памяти

100 * (1 - ((avg_over_time(node_memory_MemFree_bytes[5m]) + avg_over_time(node_memory_Cached_bytes[5m]) + avg_over_time(node_memory_Buffers_bytes[5m])) / avg_over_time(node_memory_MemTotal_bytes[5m])))

- Количество места на файловой системе

node_filesystem_avail_bytes
