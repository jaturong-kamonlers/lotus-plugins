# Lotus IDE — Plugin Catalog

Default plugin catalog for [Lotus IDE](https://github.com/jaturong-kamonlers/LotusIDE-Releases) v1.5.0+.

Open the IDE → **Lotus → Plugins → Available** → click **Fetch catalog** to install any of the plugins below.

## Categories

- **🟦 Sensors** — BH1750, BMP280, DHT, DS18B20 (AVR), GY-87, HMC5883L, MLX90614, MPU6050, DS1307 RTC (AVR), HC-SR04 Ultrasonic
- **🟧 Actuators** — PCA9685 16ch PWM, Servo Motor
- **🟪 Vision** — HuskyLens AI Camera
- **🟩 Motion** — Robot Arm IK (2/3/4-DOF), Line Follower PID

Each plugin entry in `catalog.json` declares the categories and platforms it supports. The IDE filters the Available tab by your selected board automatically — AVR-only plugins are hidden when an ESP32 board is selected, and vice versa.

## Repository layout

```
catalog.json          ← The default catalog the IDE fetches on first open.
icons/<name>.svg      ← Schematic SVG icon for each plugin (32×32).
Lotus<Name>.zip       ← The actual plugin package — manifest + index.js + src/.
```

## Updating a plugin

1. Update the source folder under `LotusIDE/plugins-converted/<name>/`.
2. Re-zip with `Compress-Archive` (Windows) or `zip -r` (Unix).
3. Replace `Lotus<name>.zip` here and bump `version` in `catalog.json`.
4. Commit + push to `main` — IDE installs pick up the new version next time the user clicks **Available → Fetch catalog**.
