import bluebuddy

# Set the Bluetooth device's MAC address
device_mac = "00:11:22:33:44:55"

# Set the password for the device
device_password = "1234"

# Create a BlueBuddy object
bb = bluebuddy.BlueBuddy()

# Connect to the device
bb.connect(device_mac, device_password)

# Get the device's services
services = bb.get_services()

# Get the device's characteristics
characteristics = bb.get_characteristics(services[0])

# Read the device's characteristics
for characteristic in characteristics:
    print(characteristic.read())

# Write to the device's characteristics
bb.write_characteristic(characteristics[0], "Hello, world!")

# Disconnect from the device
bb.disconnect()
