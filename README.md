# Home Energy Management System with an OPC UA Server Interface

This Home Energy Management System (HEMS) is an OPC UA Server capturing energy telemetry data from a photovoltaik system and a smart meter and controlling an EV wallbox with the surplus energy available from local production. This is running in Docker containers (pre-built Intel x64 and ARMx64 containers are available). 

## Future Extensions
As a next step, a heat pump will also be managed by the system and (once this is available in 2023) the connected EV battery will be used as an additional energy source during the night via Vechile-to-Home (V2H) leveraging EEBUS (see seperate EEBus.Net repo for a reference implementation).

## Telemetry Data Captured
1. Weather data from [www.openweathermap.org](http://www.openweathermap.org), as the weather impacts PV performance.
2. Telemetry data from the PV’s inverter (The inverter uses the [Fronius API](https://www.fronius.com/en/photovoltaics/products/all-products/system-monitoring/open-interfaces/fronius-solar-api-json-)). A [SunSpec](https://sunspec.org)-compliant version using ModbusTCP is in the works.
3. Smart meter telemetry data leveraging its [IEC 62056-21 standard](https://en.wikipedia.org/wiki/IEC_62056) optical interface using [a USB reader](https://shop.weidmann-elektronik.de/index.php?page=product&info=24). IEC 62056-21 uses the Smart Message Language - [SML](https://wiki.wireshark.org/SML).
4. Wallbe wallbox configuration using surplus energy from the PV to charge an Electric Vehicle.
5. IDM heat pump integration is currently ongoing.

Telemetry is made available via an OPC UA server interface.
