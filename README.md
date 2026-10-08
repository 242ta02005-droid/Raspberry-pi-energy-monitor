# Raspberry-pi-energy-monitor
import time
from datetime import datetime

# Replace this with your PZEM library/import
# depending on the PZEM-004T version you have.

def read_energy():
    # Example values for demonstration
    voltage = 230.0
    current = 1.25
    power = voltage * current
    energy = 0.125
    frequency = 50.0
    power_factor = 0.98

    return voltage, current, power, energy, frequency, power_factor


while True:
    try:
        voltage, current, power, energy, frequency, pf = read_energy()

        print("\n==============================")
        print("     RASPBERRY PI ENERGY")
        print("          MONITOR")
        print("==============================")
        print("Time       :", datetime.now().strftime("%Y-%m-%d %H:%M:%S"))
        print(f"Voltage    : {voltage:.1f} V")
        print(f"Current    : {current:.2f} A")
        print(f"Power      : {power:.1f} W")
        print(f"Energy     : {energy:.3f} kWh")
        print(f"Frequency  : {frequency:.1f} Hz")
        print(f"Power Factor: {pf:.2f}")
        print("==============================")

        time.sleep(2)

    except KeyboardInterrupt:
        print("\nMonitor stopped.")
        break
