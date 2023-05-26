# Bluetooth

**Bluetooth** is a standard for the short-range wireless interconnection of cellular phones, computer, and other electronic devices. In Linux, the canonical implementation of the Bluetooth protocol stact is `BlueZ`.

## Installation

1. Install the **bluez** package, providing the Bluetooth protocol stack.
2. Install the **bluez-utils** package, providing the `bluetoothctl` utility.
3. **Start/enable** `bluetooth.service`.

## Pairing

**Note**: Before using the Bluetooth device, make sure that it is not blocked by `rfkill`.

``` sh
rfkill unblock bluetooth
```

Start the `bluetoothctl` interactive command. Input `help` to get a list of available commands.

1. (optional) Select a default controller with `select MAC_address` (tab completion works).
2. (optional) Enter `power on` to turn the power to the controller on if the device is set to off. It is on by default.
3. Enter `devices` to get the MAC address of the device with which to pair.
4. Enter device discovery mode with `scan on` command if device is not yet on the list.
5. Turn the agent on with `agent on` or choose a specific agent.
6. Enter `pair MAC_address` to do the pairing (tab completion works).
7. If using a device without a PIN, one may need to manually trust the device before it can reconnect successfully. Enter `trust MAC_address` to do so.
8. Enter `connect MAC_address` to establish a connection.
9. DONE!
