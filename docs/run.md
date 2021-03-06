##### run PATH [ARG1] [ARG2] ...

Runs another bashible script using "source". Avoids multiple parsing of bashible itself.
The sourced script runs in a new subprocess, therefore it won't affect the caller.

Use [unless_already](unless_already.md) to prevent multiple runs.

Use [delayed](delayed.md) to postpone run. Delayed tasks will run when the top-level script finishes.

```bash
@ Prerequisities
  - run ./system_base.bash
  - run ./install-redis.bash
  - run ./install-nginx.bash

@ Creating a virtual host
  - run ./create-virtual-host.bash example.com
  - delayed unless_already systemd nginx reload
```

##### See also

[unless_already](unless_already.md)  
[delayed](delayed.md)  
