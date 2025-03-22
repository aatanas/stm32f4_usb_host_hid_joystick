## STM32F4 USB HOST HID JOYSTICK

This project controls a USB Hid Joystick using the USB Host function in STM32F401CCU.



### Test Environment
    STM32CubeIDE : 1.7.0 (Build: 10852_20210715_0634(UTC))



### Pin specifications

![](./assets/muc_pinout.png)

Output general debug messages on UART1.

Joystick status is transmitted as UART Packet on UART2.


    UART2 Protocol 

    [STX] [ID] [LEN] [DATA..] [XOR CHECKSUM] [ETX]

    STX: 0xAA
    ETX: 0x55

UART2 DATA structure
    
    typedef struct _HID_JOYSTICK_Info
    {
        uint8_t              left_axis_x;  // INDEX 1 Byte
        uint8_t              left_axis_y;  // INDEX 2 Byte
        uint8_t              right_axis_x; // INDEX 3 Byte
        uint8_t              right_axis_y; // INDEX 4 Byte

        uint8_t              pad_arrow:4;  // INDEX 5 Byte
        uint8_t              left_hat:1;
        uint8_t              right_hat:1;
        uint8_t              select:1;
        uint8_t              start:1;

        uint8_t              pad_a:1;      // INDEX 6 Byte
        uint8_t              pad_b:1;
        uint8_t              pad_x:1;
        uint8_t              pad_y:1;
        uint8_t              reserved:4;

        uint8_t              l1:1;         // INDEX 7 Byte
        uint8_t              l2:1; 
        uint8_t              r1:1;
        uint8_t              r2:1;
    } HID_JOYSTICK_Info_TypeDef;
    



[Watch the YouTube demo video](https://www.youtube.com/watch?v=UHCHiru6jNc&t=16s)



### What it actually looks like connected

![](./assets/pic0.jpg)

![](./assets/pic1.png)

![](./assets/pic2.jpg)

![](./assets/pic3.jpg)

![](./assets/pic4.jpg)

![](./assets/pic5.png)
