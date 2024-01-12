# sched-ext-systemd

### Location of systemd services

Please put systemd services in the following location:

```
/etc/systemd/system/
```

### Service start systemd scx_nest
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
systemctl status sched-ext-nest.service
● sched-ext.service - Open scx_nest
     Loaded: loaded (/etc/systemd/system/sched-ext.service; enabled; preset: disabled)
     Active: activating (start) since Thu 2024-01-11 17:42:46 CET; 11h ago
   Main PID: 520 (scx_nest)
      Tasks: 1 (limit: 35950)
     Memory: 1.5M (peak: 10.7M)
        CPU: 2.235s
     CGroup: /system.slice/sched-ext.service
             └─520 /usr/bin/scx_nest

sty 12 05:17:11 hp-laptop scx_nest[520]: Consume stats
sty 12 05:17:11 hp-laptop scx_nest[520]: -------------
sty 12 05:17:11 hp-laptop scx_nest[520]: CONSUMED=103762468
sty 12 05:17:11 hp-laptop scx_nest[520]: NOT_CONSUMED=346714589
sty 12 05:17:11 hp-laptop scx_nest[520]: Masks
sty 12 05:17:11 hp-laptop scx_nest[520]: -----
sty 12 05:17:11 hp-laptop scx_nest[520]: PRIMARY  ( 6): | *---*-**-----*-* |
sty 12 05:17:11 hp-laptop scx_nest[520]: RESERVED ( 4): | --------****---- |
sty 12 05:17:11 hp-laptop scx_nest[520]: OTHER    ( 6): | -***-*------*-*- |
sty 12 05:17:11 hp-laptop scx_nest[520]: IDLE     ( 6): | -******--------- |

```

### New enhancement

```
ConditionPathExists=/sys/kernel/debug/sched/ext
```

This will cause that when the user switches to another kernel, there will be no systemctl errors. There will be a short message that the service was not started because the conditions were not met.
