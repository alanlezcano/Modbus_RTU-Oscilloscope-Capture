# Modbus RTU Signal Analysis Using SIGLENT SDS1000X-E

## Signal Analysis Procedure Summary

- The signal was measured using **Channel 1** of the oscilloscope.

### Connection Setup:
- **Probe tip (CH1)** connected to **RS-485 A+ (Data +)**.
- **Probe ground** connected to **RS-485 GND**.

### Oscilloscope Settings:
- **Horizontal scale (Time/Div):** 2000 µs (2 ms/div)
- **Vertical scale (Volts/Div):** 2 V

### Trigger Configuration:
- **Type:** Edge
- **Slope:** Rising
- **Trigger level:** Adjusted slightly above 0 V to detect valid signal transitions.
- **Mode:** Single (to capture one complete communication event)

### Purpose of Configuration:
- Capturing the **first rising edge** of the signal, which marks the start of the master’s request.
- This setup allows clear observation of both the **Modbus master request** followed by the **slave response** in the same waveform capture.

### Result:
- The oscilloscope successfully displayed the Modbus RTU master request followed by the slave response, making it possible to visually analyze the communication sequence and signal timing.
![Osciloscopio RS-485](./IMG_1009.jpg)
## CSV File Description

The CSV file saved from the oscilloscope contains raw waveform data captured during a Modbus RTU communication event. Specifically, it records both the **master request** and the **slave response** signals measured on the RS-485 A+ line.

### CSV Structure:
- **First column:** Time values in seconds or microseconds (depending on oscilloscope settings).
- **Second column:** Voltage values in volts, corresponding to the signal level at each time point.

### What the Data Represents:
- The initial portion of the data corresponds to the **Modbus master request frame**.
- Following a brief idle period, the second portion corresponds to the **Modbus slave response frame**.
- By graphing this data in software like Excel, LibreOffice Calc, or MATLAB, you can visualize the exact timing, pulse width, and signal integrity of both communication frames.

### Notes:
- Time resolution depends on the horizontal scale and memory depth set during capture.
- Voltage values reflect single-ended measurement between RS-485 A+ and ground.

