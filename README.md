# Proclogger

The proclogger tool logs the creation, removal and renaming of processes.

For example, it enables you to:

* Check if your cronjobs are started the way you expect them.
* Verify that your maintenance daemons are running the way you expect them (e.g. PostgreSQL autovacuum).
* Educate your audience to never provide passwords as command line arguments.  (If you demonstrate this issue with `top`, your audience might think "oh, it appears just shortly, perhaps nobody will notice."  But a logging tool makes the problem obvious.)

This tool is for you, if you:

* Often run `top` just to observe which processes are started and how long they run.
* Decrease the refresh time of `top` down to the sub-second range, so you don't miss short running processes.
* Try hard to read the `top` list fast enough before items vanish.
* Try hard to observe processes that change their command line at runtime.

## Limitations

At the moment, this tool polls over `/proc` with maximum speed.  While this approach is very simple and straight forward, it has two serious drawbacks: high CPU usage and yet the risk to miss parts of fast changes.

Any pull requests to implement a more efficient and more reliable approach are welcome.
