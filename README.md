# IOT Broker

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/521c13c4f76f49e0b091b94bb18448fd)](https://app.codacy.com/manual/bernarma/pypi-fitness-broker?utm_source=github.com&utm_medium=referral&utm_content=bernarma/pypi-fitness-broker&utm_campaign=Badge_Grade_Settings)

* Include Architecture Diagram of Major Components

To run tests: python -m unittest test.test_main

To run main program: python -m iot_processor.main -c iot.config

Before running the test - start mosquitto (assume it's localhost 1883)

Ubuntu: install "mosquitto" package

## All Task List
- [ ] Automated Build/Deployment to RaspberryPI
    - Build Raspbian img
    - ???

## IOT Broker Task List
- [ ] Add Bluetooth Controller (support for multiple???)
- [ ] Add ANT+ Controller (support for multiple???)
- [ ] Integrate Controller into Event Loop
- [ ] Add commands: Start/Stop Processing Loop, Discover Devices (BT & ANT+)
- [ ] Create systemd Service
- [ ] Add Coverage.py (unit testing)
- [ ] Fork PyAnt with changes to support Python 3 (contribute modifications)
- [ ] Implement BTLE and ANT+ (support for HRM, Cadence, Speed, Power, ANT-FEC, FTMS)
- [ ] Implement Ant+ over Bluetooth for Tacx Trainers: <https://github.com/abellono/tacx-ios-bluetooth-example>
- [ ] Test Tacx Ant+ USB

## Web Server Task List
- [ ] No activities required yet

## Web UI Task List
- [ ] Add Prettier and eslint (with airbnb) based on sandbox projects
- [ ] Mockup Device Pairing Dashboard
- [ ] Mockup Workout Dashboard
- [ ] Create Unit Tests for Vue.js APP
- [ ] Create Command Generator (in JS unit tests)

## Other

Generate protobuf files:

C:\Develop\protoc-3.11.4-win64\bin\protoc.exe --proto_path .\iot_processor\messages -I C:\Develop\mtns_iot iot_processor\messages\*.proto  --python_out=iot_processor\messages

Generate JSON file for web:
.\web\client\node_modules\.bin\pbjs .\iot_processor\messages\example.proto > .\web\client\public\json\messages.json

Create SystemD Service (Python)
<https://github.com/torfsen/python-systemd-tutorial>


## Windows 10
pip install PyBluez-win10 (need to see if this is the only thing to install on Windows 10 to enable BT)

```json
[{'host': '38:F9:D3:9B:8A:97', 'name': b'OBEX Object Push', 'description': '', 'port': 10, 'protocol': 'RFCOMM', 'rawrecord': b'5y\t\x00\x00\n\x00\x01\x00\n\t\x00\x015\x03\x19\x11\x05\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\n5\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x05\t\x01\x00\t\x01\x00%\x10OBEX Object Push\t\x03\x035\x02\x08\xff\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'1105'], 'profiles': [(b'1105', 256)], 'provider': None, 'service-id': None, 'handle': 65546}, {'host': '38:F9:D3:9B:8A:97', 'name': b'Headset Audio Gateway', 'description': '', 'port': 4, 'protocol': 'RFCOMM', 'rawrecord': b'5a\t\x00\x00\n\x00\x01\x00\x08\t\x00\x015\x06\x19\x11\x12\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x04\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x08\t\x01\x02\t\x01\x00%\x15Headset Audio Gateway', 'service-classes': [b'1112', b'1203'], 'profiles': [(b'1108', 258)], 'provider': None, 'service-id': None, 'handle': 65544}, {'host': '38:F9:D3:9B:8A:97', 'name': b'Bluetooth-Incoming-Port', 'description': '', 'port': 3, 'protocol': 'RFCOMM', 'rawrecord': b'5`\t\x00\x00\n\x00\x01\x00\x04\t\x00\x015\x03\x19\x11\x01\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x03\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x01\t\x01\x00\t\x01\x00%\x17Bluetooth-Incoming-Port', 'service-classes': [b'1101'], 'profiles': [(b'1101', 256)], 'provider': None, 'service-id': None, 'handle': 65540}, {'host': '38:F9:D3:9B:8A:97', 'name': b'Group Ad-hoc Network Service', 'description': 'PAN Group Ad-hoc Network', 'port': 15, 'protocol': 'L2CAP', 'rawrecord': b'5\xa0\t\x00\x00\n\x00\x01\x00\x02\t\x00\x015\x03\x19\x11\x17\t\x00\x045\x1e5\x06\x19\x01\x00\t\x00\x0f5\x14\x19\x00\x0f\t\x01\x005\x0c\t\x08\x00\t\x08\x06\t\x86\xdd\t\x88\x0b\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x17\t\x01\x00\t\x01\x00%\x1cGroup Ad-hoc Network Service\t\x01\x01%\x18PAN Group Ad-hoc Network\t\x03\n\t\x00\x01\t\x03\x0b\t\x00\x05', 'service-classes': [b'1117'], 'profiles': [(b'1117', 256)], 'provider': None, 'service-id': None, 'handle': 65538}, {'host': '38:F9:D3:9B:8A:97', 'name': b'OBEX File Transfer', 'description': '', 'port': 15, 'protocol': 'RFCOMM', 'rawrecord': b'5{\t\x00\x00\n\x00\x01\x00\x0b\t\x00\x015\x03\x19\x11\x06\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\x0f5\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x06\t\x01\x00\t\x01\x00%\x12OBEX File Transfer\t\x03\x035\x02\x08\xff\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'1106'], 'profiles': [(b'1106', 256)], 'provider': None, 'service-id': None, 'handle': 65547}, {'host': '38:F9:D3:9B:8A:97', 'name': b'Apple Macintosh Attributes', 'description': '', 'port': None, 'protocol': 'UNKNOWN', 'rawrecord': b'5\x83\t\x00\x00\n\x00\x02\x00\x00\t\x00\x055\x03\x19\x10\x02\t\x01\x00%\x1aApple Macintosh Attributes\t\x07\x80\x1c\xf0r. \x0f\x8bN\x90\x8c\xc2\x1bF\xf5\xf2\xef\xe2\t\x07\x81%\t<unknown>\t\x07\x82%\x0eMacBookPro15,1\t\x07\x83(\x01\t\x07\x84%\x077.0.3f5\t\x07\x85\n\x00\x00\x00\x03\t\x07\x86\x19\x124', 'services-classes': [], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 131072}, {'host': '38:F9:D3:9B:8A:97', 'name': b'A2DP Audio Source', 'description': '', 'port': 25, 'protocol': 'L2CAP', 'rawrecord': b'5j\t\x00\x00\n\x00\x01\x00\t\t\x00\x015\x03\x19\x11\n\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x195\x06\x19\x00\x19\t\x01\x03\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\r\t\x01\x03\t\x01\x00%\x11A2DP Audio Source\t\x03\x11\t\x00\x01\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'110a'], 'profiles': [(b'110d', 259)], 'provider': None, 'service-id': None, 'handle': 65545}, {'host': '38:F9:D3:9B:8A:97', 'name': b'AVRCP Target', 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'5e\t\x00\x00\n\x00\x01\x00\x03\t\x00\x015\x03\x19\x11\x0c\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x04\t\x01\x00%\x0cAVRCP Target\t\x03\x11\t\x00\x01\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'110c'], 'profiles': [(b'110e', 260)], 'provider': None, 'service-id': None, 'handle': 65539}, {'host': '38:F9:D3:9B:8A:97', 'name': None, 'description': '', 'port': None, 'protocol': 'UNKNOWN', 'rawrecord': b'5W\t\x00\x00\n\x00\x01\x00\x01\t\x00\x015\x03\x19\x12\x00\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x02\x00\t\x01\x03\t\x02\x01\t\x00L\t\x02\x02\tJ\x00\t\x02\x03\t\x10\x11\t\x02\x04(\x01\t\x02\x05\t\x00\x01\t\xa0\x00\x12\x01\xb0\x16\xc4\t\xaf\xff\t\x00\x01', 'service-classes': [b'1200'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65537}, {'host': 'F4:D1:08:8E:AE:A3', 'name': b'Service Discovery\x00', 'description': 'Publishes services to remote devices', 'port': 1, 'protocol': 'L2CAP', 'rawrecord': b'5\x98\t\x00\x00\n\x00\x00\x00\x00\t\x00\x015\x03\x19\x10\x00\t\x00\x045\r5\x06\x19\x01\x00\t\x00\x015\x03\x19\x00\x01\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x01\x00%\x12Service Discovery\x00\t\x01\x01%%Publishes services to remote devices\x00\t\x01\x02%\nMicrosoft\x00\t\x02\x005\x03\t\x01\x00\t\x02\x01\n\x00\x00\x00\x18', 'service-classes': [b'1000'], 'profiles': [], 'provider': b'Microsoft\x00', 'service-id': None, 'handle': 0}, {'host': 'F4:D1:08:8E:AE:A3', 'name': b'Device ID Service Record', 'description': 'Device ID Service Record', 'port': 1, 'protocol': 'L2CAP', 'rawrecord': b'5\x95\t\x00\x00\n\x00\x01\x00\x00\t\x00\x015\x03\x19\x12\x00\t\x00\x045\r5\x06\x19\x01\x00\t\x00\x015\x03\x19\x00\x01\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x01\x00%\x18Device ID Service Record\t\x01\x01%\x18Device ID Service Record\t\x02\x00\t\x01\x03\t\x02\x01\t\x00\x06\t\x02\x02\t\x00\x01\t\x02\x03\t\n\x00\t\x02\x04(\x01\t\x02\x05\t\x00\x01', 'service-classes': [b'1200'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65536}, {'host': 'F4:D1:08:8E:AE:A3', 'name': b'Personal Ad Hoc User Service\x00', 'description': 'Personal Ad Hoc User Service', 'port': 15, 'protocol': 'L2CAP', 'rawrecord': b'5\x9d\t\x00\x00\n\x00\x01\x00\x01\t\x00\x015\x03\x19\x11\x15\t\x00\x045\x1b5\x06\x19\x01\x00\t\x00\x0f5\x11\x19\x00\x0f\t\x01\x005\t\t\x08\x00\t\x86\xdd\t\x08\x06\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x15\t\x01\x00\t\x01\x00%\x1dPersonal Ad Hoc User Service\x00\t\x01\x01%\x1dPersonal Ad Hoc User Service\x00\t\x03\n\t\x00\x00', 'service-classes': [b'1115'], 'profiles': [(b'1115', 256)], 'provider': None, 'service-id': None, 'handle': 65537}, {'host': 'F4:D1:08:8E:AE:A3', 'name': b'Audio Source', 'description': '', 'port': 25, 'protocol': 'L2CAP', 'rawrecord': b'5Y\t\x00\x00\n\x00\x01\x00\x02\t\x00\x015\x03\x19\x11\n\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x195\x06\x19\x00\x19\t\x01\x03\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\r\t\x01\x03\t\x01\x00%\x0cAudio Source', 'service-classes': [b'110a'], 'profiles': [(b'110d', 259)], 'provider': None, 'service-id': None, 'handle': 65538}, {'host': 'F4:D1:08:8E:AE:A3', 'name': b'Audio Video Remote Control Profile', 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'5\x8c\t\x00\x00\n\x00\x01\x00\x03\t\x00\x015\x03\x19\x11\x0c\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x06\t\x00\r5\x125\x105\x06\x19\x01\x00\t\x00\x1b5\x06\x19\x00\x17\t\x01\x04\t\x01\x00%"Audio Video Remote Control Profile\t\x03\x11\t\x00\x11', 'service-classes': [b'110c'], 'profiles': [(b'110e', 262)], 'provider': None, 'service-id': None, 'handle': 65539}, {'host': 'F4:D1:08:8E:AE:A3', 'name': None, 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'5Z\t\x00\x00\n\x00\x01\x00\x04\t\x00\x015\x06\x19\x11\x0e\x19\x11\x0f\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x06\t\x00\r5\x125\x105\x06\x19\x01\x00\t\x00\x1b5\x06\x19\x00\x17\t\x01\x04\t\x03\x11\t\x00\x03', 'service-classes': [b'110e', b'110f'], 'profiles': [(b'110e', 262)], 'provider': None, 'service-id': None, 'handle': 65540}, {'host': 'F4:D1:08:8E:AE:A3', 'name': None, 'description': '', 'port': 1, 'protocol': 'RFCOMM', 'rawrecord': b"5D\t\x00\x00\n\x00\x01\x00\x05\t\x00\x015\x06\x19\x11\x1f\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x01\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x1e\t\x01\x07\t\x03\x01\x08\x01\t\x03\x11\t\x00'", 'service-classes': [b'111f', b'1203'], 'profiles': [(b'111e', 263)], 'provider': None, 'service-id': None, 'handle': 65541}, {'host': 'F4:D1:08:8E:AE:A3', 'name': None, 'description': '', 'port': 2, 'protocol': 'RFCOMM', 'rawrecord': b'5?\t\x00\x00\n\x00\x01\x00\x06\t\x00\x015\x06\x19\x11\x1e\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x02\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x1e\t\x01\x07\t\x03\x11\t\x007', 'service-classes': [b'111e', b'1203'], 'profiles': [(b'111e', 263)], 'provider': None, 'service-id': None, 'handle': 65542}, {'host': 'F4:D1:08:8E:AE:A3', 'name': b'CDP Proximal Transport', 'description': '', 'port': 3, 'protocol': 'RFCOMM', 'rawrecord': b'5R\t\x00\x00\n\x00\x01\x00\x0f\t\x00\x015\x11\x1c\xc7\xf9G\x13\x89\x1eIj\xa0\xe7\x98:\tF\x12n\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x03\t\x00\x055\x03\x19\x10\x02\t\x01\x00%\x16CDP Proximal Transport', 'service-classes': ['C7F94713-891E-496A-A0E7-983A0946126E'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65551}, {'host': '38:F9:D3:25:C1:9D', 'name': b'OBEX File Transfer', 'description': '', 'port': 15, 'protocol': 'RFCOMM', 'rawrecord': b'5{\t\x00\x00\n\x00\x01\x00\n\t\x00\x015\x03\x19\x11\x06\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\x0f5\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x06\t\x01\x00\t\x01\x00%\x12OBEX File Transfer\t\x03\x035\x02\x08\xff\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'1106'], 'profiles': [(b'1106', 256)], 'provider': None, 'service-id': None, 'handle': 65546}, {'host': '38:F9:D3:25:C1:9D', 'name': b'A2DP Audio Source', 'description': '', 'port': 25, 'protocol': 'L2CAP', 'rawrecord': b'5j\t\x00\x00\n\x00\x01\x00\x08\t\x00\x015\x03\x19\x11\n\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x195\x06\x19\x00\x19\t\x01\x03\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\r\t\x01\x03\t\x01\x00%\x11A2DP Audio Source\t\x03\x11\t\x00\x01\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'110a'], 'profiles': [(b'110d', 259)], 'provider': None, 'service-id': None, 'handle': 65544}, {'host': '38:F9:D3:25:C1:9D', 'name': b'Bluetooth-Incoming-Port', 'description': '', 'port': 3, 'protocol': 'RFCOMM', 'rawrecord': b'5`\t\x00\x00\n\x00\x01\x00\x04\t\x00\x015\x03\x19\x11\x01\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x03\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x01\t\x01\x00\t\x01\x00%\x17Bluetooth-Incoming-Port', 'service-classes': [b'1101'], 'profiles': [(b'1101', 256)], 'provider': None, 'service-id': None, 'handle': 65540}, {'host': '38:F9:D3:25:C1:9D', 'name': b'Group Ad-hoc Network Service', 'description': 'PAN Group Ad-hoc Network', 'port': 15, 'protocol': 'L2CAP', 'rawrecord': b'5\xa0\t\x00\x00\n\x00\x01\x00\x02\t\x00\x015\x03\x19\x11\x17\t\x00\x045\x1e5\x06\x19\x01\x00\t\x00\x0f5\x14\x19\x00\x0f\t\x01\x005\x0c\t\x08\x00\t\x08\x06\t\x86\xdd\t\x88\x0b\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x17\t\x01\x00\t\x01\x00%\x1cGroup Ad-hoc Network Service\t\x01\x01%\x18PAN Group Ad-hoc Network\t\x03\n\t\x00\x01\t\x03\x0b\t\x00\x05', 'service-classes': [b'1117'], 'profiles': [(b'1117', 256)], 'provider': None, 'service-id': None, 'handle': 65538}, {'host': '38:F9:D3:25:C1:9D', 'name': b'Apple Macintosh Attributes', 'description': '', 'port': None, 'protocol': 'UNKNOWN', 'rawrecord': b'5\x84\t\x00\x00\n\x00\x02\x00\x00\t\x00\x055\x03\x19\x10\x02\t\x01\x00%\x1aApple Macintosh Attributes\t\x07\x80\x1c\xf0r. \x0f\x8bN\x90\x8c\xc2\x1bF\xf5\xf2\xef\xe2\t\x07\x81%\t<unknown>\t\x07\x82%\x0eMacBookPro15,1\t\x07\x83(\x01\t\x07\x84%\x086.0.12f1\t\x07\x85\n\x00\x00\x00\x03\t\x07\x86\x19\x124', 'services-classes': [], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 131072}, {'host': '38:F9:D3:25:C1:9D', 'name': b'Headset Audio Gateway', 'description': '', 'port': 4, 'protocol': 'RFCOMM', 'rawrecord': b'5a\t\x00\x00\n\x00\x01\x00\x07\t\x00\x015\x06\x19\x11\x12\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x04\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x08\t\x01\x02\t\x01\x00%\x15Headset Audio Gateway', 'service-classes': [b'1112', b'1203'], 'profiles': [(b'1108', 258)], 'provider': None, 'service-id': None, 'handle': 65543}, {'host': '38:F9:D3:25:C1:9D', 'name': b'OBEX Object Push', 'description': '', 'port': 10, 'protocol': 'RFCOMM', 'rawrecord': b'5y\t\x00\x00\n\x00\x01\x00\t\t\x00\x015\x03\x19\x11\x05\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\n5\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x05\t\x01\x00\t\x01\x00%\x10OBEX Object Push\t\x03\x035\x02\x08\xff\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'1105'], 'profiles': [(b'1105', 256)], 'provider': None, 'service-id': None, 'handle': 65545}, {'host': '38:F9:D3:25:C1:9D', 'name': b'AVRCP Target', 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'5e\t\x00\x00\n\x00\x01\x00\x03\t\x00\x015\x03\x19\x11\x0c\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x04\t\x01\x00%\x0cAVRCP Target\t\x03\x11\t\x00\x01\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'110c'], 'profiles': [(b'110e', 260)], 'provider': None, 'service-id': None, 'handle': 65539}, {'host': '38:F9:D3:25:C1:9D', 'name': None, 'description': '', 'port': None, 'protocol': 'UNKNOWN', 'rawrecord': b'5W\t\x00\x00\n\x00\x01\x00\x01\t\x00\x015\x03\x19\x12\x00\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x02\x00\t\x01\x03\t\x02\x01\t\x00L\t\x02\x02\tJ\x00\t\x02\x03\t\x10\x11\t\x02\x04(\x01\t\x02\x05\t\x00\x01\t\xa0\x00\x12\x01\xb0\x16\xc4\t\xaf\xff\t\x00\x01', 'service-classes': [b'1200'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65537}, {'host': '38:F9:D3:59:EC:34', 'name': b'Group Ad-hoc Network Service', 'description': 'PAN Group Ad-hoc Network', 'port': 15, 'protocol': 'L2CAP', 'rawrecord': b'5\xa0\t\x00\x00\n\x00\x01\x00\x02\t\x00\x015\x03\x19\x11\x17\t\x00\x045\x1e5\x06\x19\x01\x00\t\x00\x0f5\x14\x19\x00\x0f\t\x01\x005\x0c\t\x08\x00\t\x08\x06\t\x86\xdd\t\x88\x0b\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x17\t\x01\x00\t\x01\x00%\x1cGroup Ad-hoc Network Service\t\x01\x01%\x18PAN Group Ad-hoc Network\t\x03\n\t\x00\x01\t\x03\x0b\t\x00\x05', 'service-classes': [b'1117'], 'profiles': [(b'1117', 256)], 'provider': None, 'service-id': None, 'handle': 65538}, {'host': '38:F9:D3:59:EC:34', 'name': b'Headset Audio Gateway', 'description': '', 'port': 4, 'protocol': 'RFCOMM', 'rawrecord': b'5a\t\x00\x00\n\x00\x01\x00\x07\t\x00\x015\x06\x19\x11\x12\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x04\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x08\t\x01\x02\t\x01\x00%\x15Headset Audio Gateway', 'service-classes': [b'1112', b'1203'], 'profiles': [(b'1108', 258)], 'provider': None, 'service-id': None, 'handle': 65543}, {'host': '38:F9:D3:59:EC:34', 'name': b'AVRCP Target', 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'5e\t\x00\x00\n\x00\x01\x00\x03\t\x00\x015\x03\x19\x11\x0c\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x04\t\x01\x00%\x0cAVRCP Target\t\x03\x11\t\x00\x01\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'110c'], 'profiles': [(b'110e', 260)], 'provider': None, 'service-id': None, 'handle': 65539}, {'host': '38:F9:D3:59:EC:34', 'name': b'Apple Macintosh Attributes', 'description': '', 'port': None, 'protocol': 'UNKNOWN', 'rawrecord': b'5\x83\t\x00\x00\n\x00\x02\x00\x00\t\x00\x055\x03\x19\x10\x02\t\x01\x00%\x1aApple Macintosh Attributes\t\x07\x80\x1c\xf0r. \x0f\x8bN\x90\x8c\xc2\x1bF\xf5\xf2\xef\xe2\t\x07\x81%\t<unknown>\t\x07\x82%\rMacBookAir8,1\t\x07\x83(\x01\t\x07\x84%\x086.0.14d3\t\x07\x85\n\x00\x00\x00\x03\t\x07\x86\x19\x124', 'services-classes': [], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 131072}, {'host': '38:F9:D3:59:EC:34', 'name': b'A2DP Audio Source', 'description': '', 'port': 25, 'protocol': 'L2CAP', 'rawrecord': b'5j\t\x00\x00\n\x00\x01\x00\x08\t\x00\x015\x03\x19\x11\n\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x195\x06\x19\x00\x19\t\x01\x03\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\r\t\x01\x03\t\x01\x00%\x11A2DP Audio Source\t\x03\x11\t\x00\x01\t\x07w\x1com\x98\xf2<:\x11\xd6\x95j\x00\x03\x93S\xe8X', 'service-classes': [b'110a'], 'profiles': [(b'110d', 259)], 'provider': None, 'service-id': None, 'handle': 65544}, {'host': '38:F9:D3:59:EC:34', 'name': b'Bluetooth-Incoming-Port', 'description': '', 'port': 3, 'protocol': 'RFCOMM', 'rawrecord': b'5`\t\x00\x00\n\x00\x01\x00\x04\t\x00\x015\x03\x19\x11\x01\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x03\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x01\t\x01\x00\t\x01\x00%\x17Bluetooth-Incoming-Port', 'service-classes': [b'1101'], 'profiles': [(b'1101', 256)], 'provider': None, 'service-id': None, 'handle': 65540}, {'host': '38:F9:D3:59:EC:34', 'name': None, 'description': '', 'port': None, 'protocol': 'UNKNOWN', 'rawrecord': b'5W\t\x00\x00\n\x00\x01\x00\x01\t\x00\x015\x03\x19\x12\x00\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x02\x00\t\x01\x03\t\x02\x01\t\x00L\t\x02\x02\tJ\x00\t\x02\x03\t\x10\x11\t\x02\x04(\x01\t\x02\x05\t\x00\x01\t\xa0\x00\x12\x01\xb0\x16\xc4\t\xaf\xff\t\x00\x01', 'service-classes': [b'1200'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65537}, {'host': 'C0:B8:83:C9:B7:FA', 'name': b'Service Discovery\x00', 'description': 'Publishes services to remote devices', 'port': 1, 'protocol': 'L2CAP', 'rawrecord': b'5\x98\t\x00\x00\n\x00\x00\x00\x00\t\x00\x015\x03\x19\x10\x00\t\x00\x045\r5\x06\x19\x01\x00\t\x00\x015\x03\x19\x00\x01\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x01\x00%\x12Service Discovery\x00\t\x01\x01%%Publishes services to remote devices\x00\t\x01\x02%\nMicrosoft\x00\t\x02\x005\x03\t\x01\x00\t\x02\x01\n\x00\x00\x00t', 'service-classes': [b'1000'], 'profiles': [], 'provider': b'Microsoft\x00', 'service-id': None, 'handle': 0}, {'host': 'C0:B8:83:C9:B7:FA', 'name': b'Device ID Service Record', 'description': 'Device ID Service Record', 'port': 1, 'protocol': 'L2CAP', 'rawrecord': b'5\x95\t\x00\x00\n\x00\x01\x00\x00\t\x00\x015\x03\x19\x12\x00\t\x00\x045\r5\x06\x19\x01\x00\t\x00\x015\x03\x19\x00\x01\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x01\x00%\x18Device ID Service Record\t\x01\x01%\x18Device ID Service Record\t\x02\x00\t\x01\x03\t\x02\x01\t\x00\x06\t\x02\x02\t\x00\x01\t\x02\x03\t\n\x00\t\x02\x04(\x01\t\x02\x05\t\x00\x01', 'service-classes': [b'1200'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65536}, {'host': 'C0:B8:83:C9:B7:FA', 'name': b'Audio Video Remote Control Profile', 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'5\x8c\t\x00\x00\n\x00\x01\x00+\t\x00\x015\x03\x19\x11\x0c\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x06\t\x00\r5\x125\x105\x06\x19\x01\x00\t\x00\x1b5\x06\x19\x00\x17\t\x01\x04\t\x01\x00%"Audio Video Remote Control Profile\t\x03\x11\t\x00\x11', 'service-classes': [b'110c'], 'profiles': [(b'110e', 262)], 'provider': None, 'service-id': None, 'handle': 65579}, {'host': 'C0:B8:83:C9:B7:FA', 'name': b'Audio Source', 'description': '', 'port': 25, 'protocol': 'L2CAP', 'rawrecord': b'5Y\t\x00\x00\n\x00\x01\x00,\t\x00\x015\x03\x19\x11\n\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x195\x06\x19\x00\x19\t\x01\x03\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\r\t\x01\x03\t\x01\x00%\x0cAudio Source', 'service-classes': [b'110a'], 'profiles': [(b'110d', 259)], 'provider': None, 'service-id': None, 'handle': 65580}, {'host': 'C0:B8:83:C9:B7:FA', 'name': None, 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'5Z\t\x00\x00\n\x00\x01\x00-\t\x00\x015\x06\x19\x11\x0e\x19\x11\x0f\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x06\t\x00\r5\x125\x105\x06\x19\x01\x00\t\x00\x1b5\x06\x19\x00\x17\t\x01\x04\t\x03\x11\t\x00\x03', 'service-classes': [b'110e', b'110f'], 'profiles': [(b'110e', 262)], 'provider': None, 'service-id': None, 'handle': 65581}, {'host': 'C0:B8:83:C9:B7:FA', 'name': b'Personal Ad Hoc User Service\x00', 'description': 'Personal Ad Hoc User Service', 'port': 15, 'protocol': 'L2CAP', 'rawrecord': b'5\x9d\t\x00\x00\n\x00\x01\x00.\t\x00\x015\x03\x19\x11\x15\t\x00\x045\x1b5\x06\x19\x01\x00\t\x00\x0f5\x11\x19\x00\x0f\t\x01\x005\t\t\x08\x00\t\x86\xdd\t\x08\x06\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x15\t\x01\x00\t\x01\x00%\x1dPersonal Ad Hoc User Service\x00\t\x01\x01%\x1dPersonal Ad Hoc User Service\x00\t\x03\n\t\x00\x00', 'service-classes': [b'1115'], 'profiles': [(b'1115', 256)], 'provider': None, 'service-id': None, 'handle': 65582}, {'host': 'C0:B8:83:C9:B7:FA', 'name': None, 'description': '', 'port': 1, 'protocol': 'RFCOMM', 'rawrecord': b"5D\t\x00\x00\n\x00\x01\x00/\t\x00\x015\x06\x19\x11\x1f\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x01\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x1e\t\x01\x07\t\x03\x01\x08\x01\t\x03\x11\t\x00'", 'service-classes': [b'111f', b'1203'], 'profiles': [(b'111e', 263)], 'provider': None, 'service-id': None, 'handle': 65583}, {'host': 'C0:B8:83:C9:B7:FA', 'name': None, 'description': '', 'port': 2, 'protocol': 'RFCOMM', 'rawrecord': b'5?\t\x00\x00\n\x00\x01\x000\t\x00\x015\x06\x19\x11\x1e\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x02\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x1e\t\x01\x07\t\x03\x11\t\x007', 'service-classes': [b'111e', b'1203'], 'profiles': [(b'111e', 263)], 'provider': None, 'service-id': None, 'handle': 65584}, {'host': 'C0:B8:83:C9:B7:FA', 'name': b'CDP Proximal Transport', 'description': '', 'port': 3, 'protocol': 'RFCOMM', 'rawrecord': b'5R\t\x00\x00\n\x00\x01\x00>\t\x00\x015\x11\x1c\xc7\xf9G\x13\x89\x1eIj\xa0\xe7\x98:\tF\x12n\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x03\t\x00\x055\x03\x19\x10\x02\t\x01\x00%\x16CDP Proximal Transport', 'service-classes': ['C7F94713-891E-496A-A0E7-983A0946126E'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65598}, {'host': '4C:1A:3D:71:63:19', 'name': None, 'description': '', 'port': 31, 'protocol': 'L2CAP', 'rawrecord': b'6\x000\t\x00\x00\n\x00\x01\x00\x00\t\x00\x015\x03\x19\x18\x01\t\x00\x045\x135\x06\x19\x01\x00\t\x00\x1f5\t\x19\x00\x07\t\x00\x01\t\x00\x05\t\x00\x055\x03\x19\x10\x02', 'service-classes': [b'1801'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65536}, {'host': '4C:1A:3D:71:63:19', 'name': None, 'description': '', 'port': 31, 'protocol': 'L2CAP', 'rawrecord': b'6\x000\t\x00\x00\n\x00\x01\x00\x01\t\x00\x015\x03\x19\x18\x00\t\x00\x045\x135\x06\x19\x01\x00\t\x00\x1f5\t\x19\x00\x07\t\x00\x14\t\x00\x1c\t\x00\x055\x03\x19\x10\x02', 'service-classes': [b'1800'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65537}, {'host': '4C:1A:3D:71:63:19', 'name': b'Headset Gateway\x00', 'description': '', 'port': 2, 'protocol': 'RFCOMM', 'rawrecord': b'6\x00N\t\x00\x00\n\x00\x01\x00\x03\t\x00\x015\x06\x19\x11\x12\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x02\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x08\t\x01\x02\t\x01\x00%\x10Headset Gateway\x00', 'service-classes': [b'1112', b'1203'], 'profiles': [(b'1108', 258)], 'provider': None, 'service-id': None, 'handle': 65539}, {'host': '4C:1A:3D:71:63:19', 'name': b'Handsfree Gateway\x00', 'description': '', 'port': 3, 'protocol': 'RFCOMM', 'rawrecord': b"6\x00[\t\x00\x00\n\x00\x01\x00\x04\t\x00\x015\x06\x19\x11\x1f\x19\x12\x03\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x03\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x1e\t\x01\x06\t\x01\x00%\x12Handsfree Gateway\x00\t\x03\x01\x08\x01\t\x03\x11\t\x00'", 'service-classes': [b'111f', b'1203'], 'profiles': [(b'111e', 262)], 'provider': None, 'service-id': None, 'handle': 65540}, {'host': '4C:1A:3D:71:63:19', 'name': b'AV Remote Control Target\x00', 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'6\x00\x84\t\x00\x00\n\x00\x01\x00\x05\t\x00\x015\x03\x19\x11\x0c\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x03\t\x00\r5!5\x105\x06\x19\x01\x00\t\x00\x1b5\x06\x19\x00\x17\t\x01\x045\r5\x06\x19\x01\x00\t\x10!5\x03\x19\x00\x08\t\x01\x00%\x19AV Remote Control Target\x00\t\x03\x11\t\x00\x11', 'service-classes': [b'110c'], 'profiles': [(b'110e', 259)], 'provider': None, 'service-id': None, 'handle': 65541}, {'host': '4C:1A:3D:71:63:19', 'name': b'Advanced Audio\x00', 'description': '', 'port': 25, 'protocol': 'L2CAP', 'rawrecord': b'6\x00T\t\x00\x00\n\x00\x01\x00\x06\t\x00\x015\x03\x19\x11\n\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x195\x06\x19\x00\x19\t\x01\x02\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\r\t\x01\x02\t\x01\x00%\x0fAdvanced Audio\x00\t\x03\x11\t\x00\x01', 'service-classes': [b'110a'], 'profiles': [(b'110d', 258)], 'provider': None, 'service-id': None, 'handle': 65542}, {'host': '4C:1A:3D:71:63:19', 'name': None, 'description': '', 'port': 23, 'protocol': 'L2CAP', 'rawrecord': b'6\x00i\t\x00\x00\n\x00\x01\x00\x07\t\x00\x015\x06\x19\x11\x0e\x19\x11\x0f\t\x00\x045\x105\x06\x19\x01\x00\t\x00\x175\x06\x19\x00\x17\t\x01\x04\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x0e\t\x01\x03\t\x00\r5!5\x105\x06\x19\x01\x00\t\x00\x1b5\x06\x19\x00\x17\t\x01\x045\r5\x06\x19\x01\x00\t\x10!5\x03\x19\x00\x08\t\x03\x11\t\x00\x03', 'service-classes': [b'110e', b'110f'], 'profiles': [(b'110e', 259)], 'provider': None, 'service-id': None, 'handle': 65543}, {'host': '4C:1A:3D:71:63:19', 'name': b'Android Network Access Point\x00', 'description': 'NAP', 'port': 15, 'protocol': 'L2CAP', 'rawrecord': b'6\x00\x8f\t\x00\x00\n\x00\x01\x00\x08\t\x00\x015\x03\x19\x11\x16\t\x00\x045\x185\x06\x19\x01\x00\t\x00\x0f5\x0e\x19\x00\x0f\t\x01\x005\x06\t\x08\x00\t\x08\x06\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x16\t\x01\x00\t\x01\x00%\x1dAndroid Network Access Point\x00\t\x01\x01%\x04NAP\x00\t\x03\n\t\x00\x01\t\x03\x0b\t\x00\x05\t\x03\x0c\n\x00\x13\x12\xd0', 'service-classes': [b'1116'], 'profiles': [(b'1116', 256)], 'provider': None, 'service-id': None, 'handle': 65544}, {'host': '4C:1A:3D:71:63:19', 'name': b'Android Network User\x00', 'description': 'PANU', 'port': 15, 'protocol': 'L2CAP', 'rawrecord': b'6\x00z\t\x00\x00\n\x00\x01\x00\t\t\x00\x015\x03\x19\x11\x15\t\x00\x045\x185\x06\x19\x01\x00\t\x00\x0f5\x0e\x19\x00\x0f\t\x01\x005\x06\t\x08\x00\t\x08\x06\t\x00\x055\x03\x19\x10\x02\t\x00\x065\t\ten\t\x00j\t\x01\x00\t\x00\t5\x085\x06\x19\x11\x15\t\x01\x00\t\x01\x00%\x15Android Network User\x00\t\x01\x01%\x05PANU\x00\t\x03\n\t\x00\x01', 'service-classes': [b'1115'], 'profiles': [(b'1115', 256)], 'provider': None, 'service-id': None, 'handle': 65545}, {'host': '4C:1A:3D:71:63:19', 'name': b'SMS/MMS\x00', 'description': '', 'port': 4, 'protocol': 'RFCOMM', 'rawrecord': b'6\x00`\t\x00\x00\n\x00\x01\x00\n\t\x00\x015\x03\x19\x112\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\x045\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x114\t\x01\x02\t\x01\x00%\x08SMS/MMS\x00\t\x02\x00\t\x10\x01\t\x03\x15\x08\x00\t\x03\x16\x08\x0e\t\x03\x17\n\x00\x00\x00\x7f', 'service-classes': [b'1132'], 'profiles': [(b'1134', 258)], 'provider': None, 'service-id': None, 'handle': 65546}, {'host': '4C:1A:3D:71:63:19', 'name': b'OBEX Phonebook Access Server\x00', 'description': '', 'port': 5, 'protocol': 'RFCOMM', 'rawrecord': b'6\x00p\t\x00\x00\n\x00\x01\x00\x0b\t\x00\x015\x03\x19\x11/\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\x055\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x110\t\x01\x02\t\x01\x00%\x1dOBEX Phonebook Access Server\x00\t\x02\x00\t\x10\x03\t\x03\x14\x08\x03\t\x03\x17\n\x00\x00\x02\x1f', 'service-classes': [b'112f'], 'profiles': [(b'1130', 258)], 'provider': None, 'service-id': None, 'handle': 65547}, {'host': '4C:1A:3D:71:63:19', 'name': b'Dial up Networking\x00', 'description': '', 'port': 25, 'protocol': 'RFCOMM', 'rawrecord': b'6\x00Q\t\x00\x00\n\x00\x01\x00\x0c\t\x00\x015\x06\x19\x11\x03\x19\x12\x01\t\x00\x045\x0c5\x03\x19\x01\x005\x05\x19\x00\x03\x08\x19\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x03\t\x01\x01\t\x01\x00%\x13Dial up Networking\x00', 'service-classes': [b'1103', b'1201'], 'profiles': [(b'1103', 257)], 'provider': None, 'service-id': None, 'handle': 65548}, {'host': '4C:1A:3D:71:63:19', 'name': b'OBEX Object Push\x00', 'description': '', 'port': 6, 'protocol': 'RFCOMM', 'rawrecord': b'6\x00j\t\x00\x00\n\x00\x01\x00\r\t\x00\x015\x03\x19\x11\x05\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\x065\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x05\t\x01\x02\t\x01\x00%\x11OBEX Object Push\x00\t\x02\x00\t\x10\x05\t\x03\x035\x0e\x08\x01\x08\x02\x08\x03\x08\x04\x08\x05\x08\x06\x08\xff', 'service-classes': [b'1105'], 'profiles': [(b'1105', 258)], 'provider': None, 'service-id': None, 'handle': 65549}, {'host': '4C:1A:3D:71:63:19', 'name': b'OBEX File Transfer\x00', 'description': '', 'port': 20, 'protocol': 'RFCOMM', 'rawrecord': b'6\x00S\t\x00\x00\n\x00\x01\x00\x0e\t\x00\x015\x03\x19\x11\x06\t\x00\x045\x115\x03\x19\x01\x005\x05\x19\x00\x03\x08\x145\x03\x19\x00\x08\t\x00\x055\x03\x19\x10\x02\t\x00\t5\x085\x06\x19\x11\x06\t\x01\x01\t\x01\x00%\x13OBEX File Transfer\x00', 'service-classes': [b'1106'], 'profiles': [(b'1106', 257)], 'provider': None, 'service-id': None, 'handle': 65550}, {'host': '4C:1A:3D:71:63:19', 'name': None, 'description': '', 'port': 31, 'protocol': 'L2CAP', 'rawrecord': b'6\x00>\t\x00\x00\n\x00\x01\x00\x0f\t\x00\x015\x11\x1c\xb3\xb7\xe2\x8e\xa0\x00>\x17\xbd\x86n\x97\xb9\xe2\x8c\x11\t\x00\x045\x135\x06\x19\x01\x00\t\x00\x1f5\t\x19\x00\x07\t\x00(\t\x00-\t\x00\x055\x03\x19\x10\x02', 'service-classes': ['B3B7E28E-A000-3E17-BD86-6E97B9E28C11'], 'profiles': [], 'provider': None, 'service-id': None, 'handle': 65551}]
```

Service Name: b'OBEX Object Push'
    Host:        38:F9:D3:9B:8A:97
    Description:
    Provided By: None
    Protocol:    RFCOMM
    channel/PSM: 10
    svc classes: [b'1105']
    profiles:    [(b'1105', 256)]
    service id:  None

Service Name: b'Headset Audio Gateway'
    Host:        38:F9:D3:9B:8A:97
    Description:
    Provided By: None
    Protocol:    RFCOMM
    channel/PSM: 4
    svc classes: [b'1112', b'1203']
    profiles:    [(b'1108', 258)]
    service id:  None

Service Name: b'Bluetooth-Incoming-Port'
    Host:        38:F9:D3:9B:8A:97
    Description:
    Provided By: None
    Protocol:    RFCOMM
    channel/PSM: 3
    svc classes: [b'1101']
    profiles:    [(b'1101', 256)]
    service id:  None

Service Name: b'Group Ad-hoc Network Service'
    Host:        38:F9:D3:9B:8A:97
    Description: PAN Group Ad-hoc Network
    Provided By: None
    Protocol:    L2CAP
    channel/PSM: 15
    svc classes: [b'1117']
    profiles:    [(b'1117', 256)]
    service id:  None

Service Name: b'OBEX File Transfer'
    Host:        38:F9:D3:9B:8A:97
    Description:
    Provided By: None
    Protocol:    RFCOMM
    channel/PSM: 15
    svc classes: [b'1106']
    profiles:    [(b'1106', 256)]
    service id:  None

Service Name: b'Apple Macintosh Attributes'
    Host:        38:F9:D3:9B:8A:97
    Description:
    Provided By: None
    Protocol:    UNKNOWN
    channel/PSM: None

Install mosquitto on Raspberry PI
---
sudo apt update
sudo apt install -y mosquitto mosquitto-clients
sudo systemctl enable mosquitto.service
=======
JS framework for Web 3D: <https://www.babylonjs.com/>


Installing Module on RaspberyPi
---
pip3 -m venv .env

sudo apt-get install libbluetooth-dev
sudo apt-get install python-dev
pip install PyBluez


Bluetooth GATT Services Website
---
<https://www.bluetooth.com/specifications/gatt/services/>

Gattlib - Python Module/Library
- pip install wheel
- sudo apt-get install libboost-python-dev

ANT+
- TBD

Mosquitto on Raspberry PI
- <https://theembeddedlab.com/tutorials/install-mosquitto-on-a-raspberry-pi/>


Allow RemoteSigned Scripts - PS1
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

For now this is not needed - NodeGyp (possibly need when creating website/dashboard)
<https://github.com/nodejs/node-gyp#on-windows>

See for permissions to access ANT+ USB and project to use GPIO in RPI+
<https://www.instructables.com/id/Using-Zwift-With-Nearly-Any-Fitness-Device/>

In JS Client - to generate PBJS files - .\node_modules\.bin\pbjs

