
Basic Bluetooth Concepts
- Created to replace short range wired connection
- 2 Type
	- Classic
		- Basic Rate / Enhanced Data Rate
		- More power hungry
		- speakers, headset, keyboards, etc
		- pairing required
	- BLE
		- low power consumption
		- short burst of data rather than continuous stream
		- heart rate monitor, iot, airtags, etc
		- pairing optional

Key Terminology
- Central: Device initiating the connection (client)
- Peripheral: Device that client connects to (server) / device
- GATT: Generic Attribute Profile
- Service: logical group of device capabilities
- Characteristics: describe a specific capability (read / write / notify)

Services -> has characteristics
Each service has UUID, Each characteristics has UUID

iPhone -> Scan for peripherals
Peripheral advertises data to iPhone
iPhone request connection to Peripheral
Peripheral confirms connection to iPhone

iPhone -> what services do you offer? -> Peripherals -> Heart Rate, Device Info, ... -> Which characteristics -> ...

"Notify me of all updates to the Heart Rate Measurement" -> Peripherals automatically sends heart rate periodically to iPhone

Core Bluetooth
- uses delegate pattern for asynchronous updates

Starting point for connecting to BLE
```
let cbCentralManager = CBCentralManager(delegate: self, queue: nil)
```
delegate: information about device state and connections

info.plist -> NSBluetoothAlwaysUsageDescription
Background modes

Bluetooth States (didUpdateState)
- unknown, resetting, unsuported, unauthorized, poweredOff, poweredOn

CBUUID
reference predefined uuid without having to state the long UUID

```
cbCentralManager.scanForPeripherals(withServices: [Gatt.Service.heartRate])

```

delegate didDiscover -> rssi (how close/far the peripheral is)

Connecting
```
func connect(to peripheral: CBPeripheral) {
	connectedPeripheral = peripheral
	cbCentralManager.connect(peripheral)
	stopScanning()
}
```

delegate didConnect ->

```
peripheral.discoverService
```

delegate didDiscoverServices ->

```
peripheral.discoverCharacteristics
```

delegate didDiscoverCharacteristicsFor ->

```
peripheral.setNotifyValue
```

delegate didUpdateValueFor

how to decode:
- First byte: flag that indicates the structure of the payload
- Second byte: heart rate measurement in beats per minute (BPM)


Simulating a Bluetooth Device
```
let cbPeripheralManager = CBPeripheralManager(delegate: self, queue: nil)
```

setup services and characteristics
```
let heartRateCharacteristic = CBMutableCharacteristic(
	type: Gatt.Characteristic.heartRateMeasurement,
	property: [.notify],
	value: nil,
	permissions: [.readable]
)


```



https://medium.com/@kakshata12/creating-ios-application-as-bluetooth-peripheral-669404230232