# AGILE-CLI: command line interface 

This repository contains the AGILE command line interface, a small tool to simplify deployment, development, and maintainance of
the AGILE stack from the command line.

## Usage

Use `./agile start` to start the main components, and `./agile stop` to stop them.

Once component started you can visit http://127.0.0.1:8000 to access the AGILE user interface and start building your IoT solution.

To access the gateway from LAN/WLAN, http://raspberrypi.local:8000 might work, depending on your network setup. If not, go by IP.

## Update

Use `./agile update` to download the newest version of AGILE component. Note that this is different from `git pull`, which updates the
startup scripts only.


### Updating a single component

In most cases, you can update a single coponent while other components keep running.
For example, to update agile-osjs without restarting the rest, use the following commands:
```
./agile compose stop agile-osjs
./agile compose pull agile-osjs
./agile compose up agile-osjs
```

## Troubleshooting

You can access the logs with `./agile compose logs` and view all logs.

To view per component log use `./agile compose logs <component>`

To get the list of running components use `./agile compose ps` with the pattern `compose_<component name>_1`
