SHELL = bash

upload:
	ampy -p /dev/ttyUSB0 reset
	ampy -p /dev/ttyUSB0 put sensor.py /flash/main.py
	ampy -p /dev/ttyUSB0 reset
	echo -ne "import machine; machine.reset();\r" > /dev/ttyUSB0

reset:
	ampy -p /dev/ttyUSB0 reset
	echo -ne "import machine; machine.reset();\r" > /dev/ttyUSB0

login:
	screen -L /tmp/screenlog /dev/ttyUSB0 115200


uploadlib:
	ampy -p /dev/ttyUSB0 put BitBuffer.py /flash/BitBuffer.py
	ampy -p /dev/ttyUSB0 put BMP280.py /flash/BMP280.py
	ampy -p /dev/ttyUSB0 put CBOR.py /flash/CBOR.py
	ampy -p /dev/ttyUSB0 put CoAP.py /flash/CoAP.py
	ampy -p /dev/ttyUSB0 put Compressor.py /flash/Compressor.py
	ampy -p /dev/ttyUSB0 put Decompressor.py /flash/Decompressor.py
	ampy -p /dev/ttyUSB0 put Parser.py /flash/Parser.py
	ampy -p /dev/ttyUSB0 put RuleMngt.py /flash/RuleMngt.py


runtest:
	py.test --cov=. test/
