# Digital-Clock-Controller-For-STM32
first download lcd.c and lcd.h.
create folder and write name LCD.
paste both of them in folder .
copy folder.
open the cubemx and select "STM32F103C8T6".
set pa0,pa1,pa2,pa3,pa3,pa4,pa5 to Gpio_Output and set pb0,pb1,pb3 to Gpio_Input.
Next,click generate code and waite.
paste this code in int main(void){ while (1){  /* USER CODE BEGIN 3 */



    sprintf(data, "%02d   :%02d   :%02d", saat, daghyghe, sanyeh);
    uint8_t c = HAL_GPIO_ReadPin(GPIOB, GPIO_PIN_3);
    uint8_t b = HAL_GPIO_ReadPin(GPIOB, GPIO_PIN_1);
    uint8_t d = HAL_GPIO_ReadPin(GPIOB, GPIO_PIN_0);

   
    if (c == 1) {
        HAL_Delay(200);     
        a++;
        if (a > 3) a = 1;
    }

    
    lcd_gotoxy(0,1);

    if (a == 1) {
      lcd_gotoxy(0,1);
      lcd_puts("__            ");
    }
      if (a == 2){
        lcd_gotoxy(0,1);
        lcd_puts("      __      ");
      }
        if (a == 3){
          lcd_gotoxy(0,1);
          lcd_puts("            __");
        }
    
    if (b == 1 & a == 1 ) {
        HAL_Delay(200);   
        saat++;
    }
    if (b == 1 & a == 2 ) {
        HAL_Delay(200);   
        daghyghe++;
    }
     if (b == 1 & a == 3 ) {
        HAL_Delay(200);   
        sanyeh++ ;
    }
   
     if (d == 1 & a == 1 ) {
        HAL_Delay(200);   
        saat--;
    }
    if (d == 1 & a == 2 ) {
        HAL_Delay(200);   
        daghyghe--;
    }
     if (d == 1 & a == 3 ) {
        HAL_Delay(200);   
        sanyeh-- ;
    }
    
    lcd_gotoxy(0,0);
    lcd_puts(data);
    
And paste this code one line before while (1) {

    lcd_init() ;
    lcd_clear() ;
    a=1 ;

 And redefine these variables:

    char data[17];
    uint32_t sanyeh;
    uint32_t daghyghe;
    uint32_t saat;
    uint8_t a = 1;

And at the top of the main code, in this section:

    /* Private includes ----------------------------------------------------------*/
    /* USER CODE BEGIN Includes */

 Add these two includes:

    #include "LCD/lcd.h"
    #include <stdio.h>
