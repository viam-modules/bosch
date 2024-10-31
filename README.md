# bosch

Configure a `bme280` sensor to integrate a [BME280 environmental sensor](https://www.adafruit.com/product/2652), used for sensing temperature, humidity, and barometric pressure, into your machine:

Navigate to the **CONFIGURE** tab of your machine's page in [the Viam app](https://app.viam.com).
Click the **+** icon next to your machine part in the left-hand menu and select **Component**.
Select the `sensor` type, then select the `bme280` model.
Enter a name or use the suggested name for your sensor and click **Create**.

Add the viam_bosch module, and fill in the attributes as applicable to your sensor, according to the table below.

```json {class="line-numbers linkable-line-numbers"}
{
  "components": [
    {
      "name": "<your-bme280-sensor-name>",
      "namespace": "rdk",
      "type": "sensor",
      "model": "viam:bosch:bme280",
      "attributes": {
        "i2c_bus": "<your-i2c-bus-index-on-board>",
        "i2c_address": "<your-i2c-address>"
      },
      "depends_on": []
    }
  ],
  "modules": [
    {
      "type": "registry",
      "name": "viam_bosch",
      "module_id": "viam:bosch",
      "version": "0.0.8"
    }
  ]
}
```

The following attributes are available for `bme280` sensors:

<!-- prettier-ignore -->
| Attribute | Type | Required? | Description |
| --------- | ---- | --------- | ----------  |
| `i2c_bus` | string | **Required** | The index of the I<sup>2</sup>C bus on the board that the sensor is wired to. |
| `i2c_address`  | string | Optional | Default: `0x77`. The [I<sup>2</sup>C device address](https://learn.adafruit.com/i2c-addresses/overview) of the sensor. |

## Test the sensor

After you configure your sensor, open the sensor's **TEST** panel on the [**CONFIGURE**](/configure/) or [**CONTROL**](/fleet/control/) tabs.
To access detailed readings from your sensor, click on the **Get Readings** button.

## Next steps

Check out the [sensor API](/appendix/apis/components/sensor/).
