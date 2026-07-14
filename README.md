# [`bosch` module](https://github.com/viam-modules/bosch)

This [bosch module](https://app.viam.com/module/viam/bosch) implements a
bosch [BME280 environmental sensor](https://www.adafruit.com/product/2652), used for sensing
temperature, humidity, and barometric pressure using the [
`rdk:component:sensor` API](https://docs.viam.com/appendix/apis/components/sensor/).

> [!NOTE]
> Before configuring your sensor, you must [create a machine](https://docs.viam.com/cloud/machines/#add-a-new-machine).

Navigate to the [**CONFIGURE** tab](https://docs.viam.com/configure/) of your [machine](https://docs.viam.com/fleet/machines/) in the [Viam app](https://app.viam.com/).
[Add sensor / viam:bosch:bme280 to your machine](https://docs.viam.com/configure/#components).

## Configure your bme280 sensor

For most BME280 sensors, copy and paste the following attribute template into your sensors’s attributes field on the new component panel:

```json
{
  "i2c_bus": "1",
  "i2c_addr": 119
}
```

### Attributes

The following attributes are available for `viam:bosch:bme280` sensors:

| Name       | Type   | Inclusion    | Default              | Description                                                                                |
|------------|--------|--------------|----------------------|--------------------------------------------------------------------------------------------|
| `i2c_bus`  | string | **Required** | -                    | The index of the I2C bus on the board that the sensor is wired to.                         |
| `i2c_addr` | int    | Optional     | 119 (or 0x77 as hex) | The [I2C device address](https://learn.adafruit.com/i2c-addresses/overview) of the sensor. |

### Example Readings Sample

```json
{
  "dew_point_celsius": 7.9552551384307995,
  "dew_point_fahrenheit": 46.31945924917544,
  "pressure_mpa": 674.6150820292188,
  "relative_humidity_pct": 46.86546717372174,
  "temperature_celsius": 19.598497458914327,
  "temperature_fahrenheit": 67.2772954260458
}
```

## Next Steps

- To test your sensor, expand the **TEST** section of its configuration pane or go to the [**CONTROL** tab](https://docs.viam.com/fleet/control/).
- To write code against your sensor, use one of the [available SDKs](https://docs.viam.com/sdks/).
- To view examples using a sensor component, explore [these tutorials](https://docs.viam.com/tutorials/).
