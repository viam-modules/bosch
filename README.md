# [`bosch` module](https://github.com/viam-modules/bosch)

This [bosch module](https://app.viam.com/module/viam/bosch) implements a bosch [BME280 environmental sensor](https://www.adafruit.com/product/2652), used for sensing temperature, humidity, and barometric pressure using the [`rdk:component:sensor` API](https://docs.viam.com/appendix/apis/components/sensor/).

> [!NOTE]
> Before configuring your sensor, you must [create a machine](https://docs.viam.com/cloud/machines/#add-a-new-machine).

## Configure your bme280 sensor

Navigate to the [**CONFIGURE** tab](https://docs.viam.com/configure/) of your [machine](https://docs.viam.com/fleet/machines/) in the [Viam app](https://app.viam.com/).
[Add sensor / viam:bosch:bme280 to your machine](https://docs.viam.com/configure/#components).

On the new component panel, copy and paste the following attribute template into your sensors’s attributes field:

```json
{
  "i2c_bus": "<your-i2c-bus-index-on-board>",
  "i2c_address": "<your-i2c-address>"
}
```
> [!NOTE]
> For more information, see [Configure a Machine](https://docs.viam.com/configure/).

### Attributes

The following attributes are available for `viam:bosch:bme280` sensors:

| Attribute | Type | Required? | Description |
| --------- | ---- | --------- | ----------  |
| `i2c_bus` | string | **Required** | The index of the I<sup>2</sup>C bus on the board that the sensor is wired to. |
| `i2c_address` | string | Optional | Default: `0x77`. The [I<sup>2</sup>C device address](https://learn.adafruit.com/i2c-addresses/overview) of the sensor. |

## Example configuratiosn

### `viam:bosch:bme280`
```json
  {
     "name": "<your-bosch-bme280-sensor-name>",
      "model": "viam:bosch:bme280",
      "type": "sensor",
      "namespace": "rdk",
      "attributes": {
        "i2c_bus": "<your-i2c-bus-index-on-board>",
        "i2c_address": "<your-i2c-address>"
      },
      "depends_on": []
  }
```

### Next Steps
- To test your sensor, expand the **TEST** section of its configuration pane or go to the [**CONTROL** tab](https://docs.viam.com/fleet/control/).
- To write code against your sensor, use one of the [available SDKs](https://docs.viam.com/sdks/).
- To view examples using a sensor component, explore [these tutorials](https://docs.viam.com/tutorials/).
