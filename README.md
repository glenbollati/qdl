# qdl

A script wrapping `busybox httpd` and `stunnel` to provide a lightweight and portable file sharing system.

## Examples

```
qdl serve
```
Start `httpd` and `stunnel`

```
qdl kill
```

Kill `httpd` and `stunnel`

```
qdl file /path/to/myfile name myfileforyou expire 10m
```

Serve `myfile` as `myfileforyou`. After 10 minutes, delete the file, kill `httpd` and `stunnel` and exit.
If `httpd` and `stunnel` are not already running, they will be started up for you (as if you had run `qdl serve`).

```
qdl file /path/to/myfile name myfileforyou push 10m
```

Serve `myfile` as `myfileforyou`. After 10 minutes, send a reminder over Pushover to remove the file.

**NOTE: to use Pushover, the `PUSHOVER_TOKEN` variable must be set in your environment (or set it in the script/pass it from cmdline)**

## `qdlmksite`

Is a quick and dirty script to create static html pages containing file listings for each user (except the temporary one - `tmp`).

Just set `$SRV_ROOT` and run the script, then tweak things to your liking.
