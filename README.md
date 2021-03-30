# ht16k33-stm32-hal-driver

Example usage:

```
HT16K33_HandleTypeDef led1;
I2C_HandleTypeDef hi2c3;

int main() {
    MX_I2C3_Init();
    ht16k33_init(&led1, &hi2c3, HT16K33_BASE_ADDRESS);

    while(1) {
        for(uint8_t i = 0; i < 128; i++) {
            ht16k33_set_led(&led1, i);
            ht16k33_write_display(&led1);
            HAL_Delay(10);
        }
        
        ht16k33_clear(&led1);
    }
}
```
        
