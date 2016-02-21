Welcome to Edison-BLE, an open-source BLE GATT service for Intel Edison developers using Bleno. 

## Running Edison GATT

# Step 1: Establish a serial connection to your Intel Edison 

Use SSH, screen etc, doesn't matter.

# Step 2: Download the sample GATT and copy it to your Edison

You can do this either with FileZilla or SCP or you can install Git on your Edison and pull down my repo directly. For FileZilla, go and download FileZilla and then get your Edison on the Wi-Fi network using "configure_edison --setup." Once your Edison is online, use sftp://your.edison.ip user: root password: your password. Then copy the files over. Or just SCP, doesn't matter.

# Step 3: Prepare bluetooth

On your Edison do this:

```
$ systemctl disable bluetoothd
$ rfkill unblock bluetooth
$ killall -9 bluetoothd
$ hciconfig hci0 up
$ node install
$ node edison-ble.js
```

# Step 4: Scan your BLE service with a  mobile phone

I recommend downloading the LightBlue app on your iOS phone or equivalent on your Android phone. With Android you may need to turn Blueooth off and back on again to kickstart the sucker.

Another approach is to use Noble to explore the service from your laptop.

Now you should be able to scan and read your Edison GATT service.
