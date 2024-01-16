# microcontroller_cypherlock
CypherLock for a peripheral Interface Controller built in my Microcomputer Systems class. IDE USED: XILINX (AMD NOWADAYS) VIVADO 2017.1


HEADER FILES: #include statements are used to include necessary header files like xc.h, stdio.h, stdlib.h, as well as custom files like "i2c.h" and "i2c_LCD.h". These headers contain definitions, functions, and configurations relevant to the project.

CONFIGURATION BITS: #pragma config statements are used to set the configuration bits of the microcontroller. These bits determine various settings like oscillator selection, watchdog timer, power-up timer, code protection, brown-out reset, etc.

MACROS AND DEFINITIONS: #define statements define constants and macros to be used throughout the code. For example, baud rate, oscillator frequency, and I2C slave address are defined.

FUNCTION PROTOTYPES: Prototypes for several functions are declared. These include functions related to I2C LCD control (I2C_LCD_Command, I2C_LCD_SWrite, I2C_LCD_Init, I2C_LCD_Pos, I2C_LCD_Busy), communication setup (setup_comms, putch, getch, getche), timer configuration (timer_config), and display control (Display).

MAIN FUNCTION: The main function is where the program starts executing. It initializes variables, sets up the touchpad, configures clocks and pins, and then enters an infinite loop. Within the loop, it scans four touchpads, displays the pressed button on an I2C-connected LCD, and checks if the entered password matches the expected password. The password is compared by checking if each entered digit matches the corresponding digit in the expected password. If the password is correct, it displays "Success" on the LCD; otherwise, it displays "Wrong password."

TOUCHPAD CONFIGURATION: The touchpad is set up using the CPSCON0 register, and the thresholds for touch detection are defined for each of the four touchpads.

DISPLAY FUNCTIONS: The Display function is responsible for displaying characters on the LCD based on the parameter delay. Different cases represent different buttons pressed, and the corresponding character is displayed on the LCD.

CONFIGURATION FUNCTIONS: 
clockAndpin_config function configures clock and pins, disables interrupts, and sets up Timer 0 and Timer 1.
timer_config function resets and enables Timer 1.
usartConfig function configures USART pins.
setup_comms function sets up communication parameters, such as baud rate and enable/disable status of various communication-related bits.

WHILE(1) LOOP: The main loop repeatedly scans the touchpads, updates the LCD display, and checks for the correct password. If the correct password is entered, it displays "Success" and breaks out of the loop.

SERIAL COMMUNICATION: Serial communication is set up using USART. The functions putch, getch, and getche handle the output and input of characters over serial communication.
