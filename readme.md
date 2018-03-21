# Install

In order to run the load test, Alexandria app will be run outside of Docker so that the Erlang observer can be started in the same `iex` session.

## Clean up docker containers

If you have previously run Alexandria locally with `usher run local` then you will need to clean up that running container...

`docker ps` then `docker kill` to remove running alexandria containers.

## Start Alexandria within iex

This enables the erlang observer to be running in the context of the Alexandria app.

`iex -S phx.server`

## Start observer

`:observer.start`

### Start the load test

You are now ready to run the load-test to identify memory leaks.

Assumes you are runnning the Taurus Command-Line tool [bzt](https://gettaurus.org/docs/CommandLine/#Command-Line-Tool)

`bzt alexandria.yml`

## Review running Pids for memory leaks

Refer to the observer GUI.

Check the 'Table Viewer' tab - look at the number of objects created for each request.
