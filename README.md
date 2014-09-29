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
cd fig-counterparty
fig up
```

You might need to run `fig up` twice on the first start.  This is a bug that it doesn't initialize correctly on the first start.

# Debugging

To see the bitcoind debug log (testnet): `fig run --rm bitcoind shell tail -f /bitcoin/.bitcoin/testnet3/debug.log`

To see the counterpartyd debug log (testnet): `fig run --rm counterpartyd shell tail -f /home/counterparty/.local/share/counterpartyd/counterpartyd.testnet.log`

`CTRL-C` to exit debug log.
