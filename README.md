# sched-ext-systemd

### Location of systemd services

Please put systemd services in the following location:

```
/etc/systemd/system/
```

### Management of services
```
systemctl enable sched-ext-*.service
```
```
systemctl start sched-ext-*.service
```

Below is a list of schedulers with their locations:

```
/usr/bin/scx_simple
/usr/bin/scx_qmap
/usr/bin/scx_central
/usr/bin/scx_pair
/usr/bin/scx_flatcg
/usr/bin/scx_userland
/usr/bin/scx_nest
/usr/bin/scx_layered
/usr/bin/scx_rustland
/usr/bin/scx_rusty
```

Replace * with the name of the scheduler, for example.

```
systemctl enable sched-ext-nest.service
```
```
systemctl start sched-ext-nest.service
```

You can check the status of the service as follows:

```
❯ systemctl status sched-ext-nest
● sched-ext-nest.service - Start scx_nest
    Loaded: loaded (/etc/systemd/system/sched-ext-nest.service; enabled; preset: disabled)
    Active: active (running) since Mon 2024-01-15 13:22:31 CET; 5s ago
  Main PID: 161907 (scx_nest)
     Tasks: 1 (limit: 37771)
    Memory: 1.0M (peak: 11.5M)
       CPU: 49ms
    CGroup: /system.slice/sched-ext-nest.service
            └─161907 /usr/bin/scx_nest

sty 15 13:22:35 cachyos scx_nest[161907]: Consume stats
sty 15 13:22:35 cachyos scx_nest[161907]: -------------
sty 15 13:22:35 cachyos scx_nest[161907]: CONSUMED=1667
sty 15 13:22:35 cachyos scx_nest[161907]: NOT_CONSUMED=5777
sty 15 13:22:35 cachyos scx_nest[161907]: Masks
sty 15 13:22:35 cachyos scx_nest[161907]: -----
sty 15 13:22:35 cachyos scx_nest[161907]: PRIMARY ( 3): | ***- |
sty 15 13:22:35 cachyos scx_nest[161907]: RESERVED ( 1): | ---* |
sty 15 13:22:35 cachyos scx_nest[161907]: OTHER   ( 0): | ---- |
sty 15 13:22:35 cachyos scx_nest[161907]: IDLE    ( 4): | **** |

```

### New enhancement

```
ConditionPathExists=/sys/kernel/debug/sched/ext
```

This will cause that when the user switches to another kernel, there will be no systemctl errors. There will be a short message that the service was not started because the conditions were not met.
