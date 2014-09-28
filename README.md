# Fig Counterparty

Run entire counterparty stack using Docker and Fig.

NOTE:
Currently this project will only run bitcoind and counterpartyd on the testnet.  All ports are blocked by default.  To see that things are working, create a container and tail the debug log by running the following.

```
fig run --rm counterpartyd login
tail -f ~/.local/share/counterpartyd/counterpartyd.testnet.log
```

# Requirements

- Docker
- Fig

# Quickstart

```
git clone https://github.com/dmp1ce/fig-counterparty.git
fig up
```

# Debugging

To see the bitcoind debug log (testnet): `fig run --rm bitcoind tail -f /bitcoin/.bitcoin/testnet3/debug.log`

To see the counterpartyd debug log (testnet): `fig run --rm counterpartyd shell tail -f /home/counterparty/.local/share/counterpartyd/counterpartyd.testnet.log`

`CTRL-C` to exit.
