# Open-systemd-service-scx_nest

### My location systemd service scx_nest

```
/etc/systemd/system/sched-ext.service
```

### Service start systemd scx_nest
```
systemctl enable sched-ext.service
```
```
systemctl start sched-ext.service
```
```
systemctl status sched-ext.service
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
