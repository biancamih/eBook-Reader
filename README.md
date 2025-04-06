# OpenBook 
**Autor: Mihai Bianca-Ioana**

## Diagrama Bloc
```
                            +------------------------+
                            | USB-C Connector & ESD  |
                            +------------------------+
                                      |
                                      v
                             +------------------+
                             |   LDO Regulator   |
                             +------------------+
                                      |
                                      v
 +-------------------+       +------------------+       +---------------------+
 | Li-Po Charging IC | ----> | ESP32-C6 WROOM-1 | <-->  |    SD Card          |
 +-------------------+       +------------------+       +---------------------+
                                      |  ^   ^  ^
                                      |  |   |  |
         +------------------+         |  |   |  +---------------------+
         | Environmental     | -------+  |   +----------------+       |
         | Sensor (BME688)   |            |                    |       |
         +------------------+            |  +--------------+  |       |
                                         +->| NOR Flash     |<-+       |
                                         |  +--------------+          |
                                         |                             |
             +---------------+           +->| Battery Gauge |          |
             |   E-Paper     |<--------------+ (MAX17048)   |          |
             |   Driver      |           |  +---------------+          |
             +---------------+           |                             |
                                         +->| RTC (DS3231)  |<---------+
                                         |
                                         +->| Buttons       |
                                            +---------------+
```



## Bill Of  Materials (BOM)
| Component Name                            | Link                                                                                                   | Datasheet Link                                                                                           |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 112ATAARR03ATTEND                        | [Link](https://store.comet.srl.ro/Catalogue/Product/43497/)                                                | [Link](https://www.attend.com.tw/data/download/file/112A-TAAR-R03.rar)                                   |
| ADAFRUIT_CHIP-LED0603                    | [Link](https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/view-part/?ref=search&t=LED%200603)           | [Link](https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/datasheet/)                                 |
| CAPCP3225X100N                           | [Link](https://www.snapeda.com/parts/CPH3225A/Seiko+Instruments/view-part/?ref=eda)                        | [Link](https://www.snapeda.com/parts/CPH3225A/Seiko%20Instruments/datasheet/)                            |
| DIOC1608X36N                             | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda)                           | [Link](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse%20Inc./datasheet/)                          |
| EAGLE-LTSPICE_C0402                      | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                 | [Link](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                              |
| ESP32_WROVER_AVX---SD0805S020S1R0_AVX_0  | [Link](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D) | [Link](https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf)                                        |
| ESP32_WROVER_BME680_PSON80P300X300X100-8N| [Link](https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home)                                 | [Link](https://www.snapeda.com/parts/BME680/Bosch%20Sensortec/datasheet/)                                |
| ESP32_WROVER_EAGLE-LTSPICE_C0402         | [Link](https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO)                                 | [Link](https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf)                              |
| ESP32_WROVER_EAGLE-LTSPICE_R0402         | [Link](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO)       | [Link](https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf)|
| ESP32_WROVER_SPARKFUN-DISCRETESEMI_SOT23-3| [Link](https://componentsearchengine.com/part-view/DMG2305UX-7/Diodes%20Incorporated)                      | [Link](https://www.diodes.com//assets/Datasheets/DMG2305UX.pdf)                                          |
| ESP32_WROVER_SPARKFUN-IC-POWER_SOT23-5   | [Link](https://ro.mouser.com/ProductDetail/Microchip-Technology/MCP73831T-5ACI-OT?qs=hH%252BOa0VZEiAcgAcEkuamXg%3D%3D) | [Link](https://ro.mouser.com/datasheet/2/268/MCP73831_Family_Data_Sheet_DS20001984H-3441711.pdf)         |
| ESP32C6_VARISTOR_CT/CN1812               | [Link](https://ro.mouser.com/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D)     | [Link](https://www.tdk-electronics.tdk.com/inf/75/db/CTVS_14/Surge_protection_series.pdf)                |
| FH34SRJ24S05SH99                         | [Link](https://ro.mouser.com/ProductDetail/Hirose-Connector/FH34SRJ-24S-0.5SH99?qs=vcbW%252B4%252BSTIpKBl5ap9J8Fw%3D%3D) | [Link](https://ro.mouser.com/datasheet/2/185/FH34SRJ_24S_0_5SH_99__CL0580_1255_6_99_2DDrawing_0-1615044.pdf)|
| IND_4828-WE-TPC_WRE                      | [Link](https://ro.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D)  | [Link](https://www.we-online.com/components/products/datasheet/744043680.pdf)                            |
| JST04_1MM_RA                             | [Link](https://ro.mouser.com/ProductDetail/Adafruit/4208?qs=PzGy0jfpSMtbScLbr0L5dw%3D%3D)                   | [Link](https://ro.mouser.com/ProductDetail/Adafruit/4208?qs=PzGy0jfpSMtbScLbr0L5dw%3D%3D)                 |
| MYBUTTON                                 | [Link](https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k)      | [Link](https://industry.panasonic.com/global/en/downloads?tab=catalog&small_g_cd=203&part_no=EVQPUJ02K)  |
| RCL_CT3528                               | [Link](https://www.snapeda.com/parts/TAJB475K025RNJ/AVX/view-part/?t=capacitor%203528&con_ref=None)        | [Link](https://www.snapeda.com/parts/TAJB475K025RNJ/AVX/datasheet/)                                      |
| SAMACSYS_PARTS_USB4110GFA                | [Link](https://componentsearchengine.com/part-view/USB4110-GF-A/GCT%20(GLOBAL%20CONNECTOR%20TECHNOLOGY))   | [Link](https://gct.co/files/drawings/usb4110.pdf)                                                         |
| SOD3716X135N                             | [Link](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D) | [Link](https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf)                                        |
| SOIC127P1032X265-16N                     | [Link](https://eu.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D)  | [Link](https://www.snapeda.com/parts/DS3231SN%23/Analog%20Devices/datasheet/)                            |
| SON127P600X800X80-9N                     | [Link](https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond+Electronics/view-part/?ref=eda)                 | [Link](https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond%20Electronics/datasheet/)                      |
| SON50P200X200X80-9N                      | [Link](https://www.snapeda.com/parts/MAX17048G+T10/Analog+Devices/view-part/?ref=eda)                      | [Link](https://www.snapeda.com/parts/MAX17048G+T10/Analog%20Devices/datasheet/)                          |
| SOT65P210X110-3N                         | [Link](https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay)                                 | [Link](https://componentsearchengine.com/Datasheets/1/SI1308EDL-T1-GE3.pdf)                               |
| SOT95P280X125-5N                         | [Link](https://componentsearchengine.com/part-view/BD5229G-TR/ROHM%20Semiconductor)                         | [Link](https://datasheet.datasheetarchive.com/originals/distributors/Datasheets_SAMA/f2b9741ef86007909f138d561a359946.pdf) |
| SOT95P280X145-6N                         | [Link](https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda)                   | [Link](https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/datasheet/)                         |
| XCVR_ESP32-C6-WROOM-1-N8                 | [Link](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda)             | [Link](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif%20Systems/datasheet/)                 |


## Descriere functionala hardware 

###  Arhitectura Hardware

Sistemul este bazat pe microcontrollerul **ESP32-C6-WROOM-1**, cu conectivitate Wi-Fi 6 și BLE, gândit pentru funcționare autonomă și consum redus de energie. Dispozitivul este alimentat de la o baterie Li-Po și poate fi programat prin USB-C. Componentele sunt interconectate prin SPI, I2C și GPIO.

---

### Alimentare și management baterie

- **USB-C Connector & ESD Protection**  
  Conector: `USB4110-GF-A`  
  Protecție ESD: `USBLC6-2SC6Y`

- **LDO Voltage Regulator**  
  Asigură 3.3V stabil pentru întreaga placă

- **Li-Po Battery Charger**  
  MCP73831 – circuit dedicat pentru încărcarea bateriei

- **Battery Gauge (MAX17048)**  
  Măsoară nivelul bateriei și comunică prin I2C

---

### Microcontroller principal

- **ESP32-C6-WROOM-1-N8**  
  RISC-V MCU cu Wi-Fi 6, BLE, 8MB flash intern  
  Rol: control central, comunicare cu senzori, logare, afișare

---

### Stocare

- **SD Card** – pentru loguri de date, firmware, fișiere
- **W25Q512 NOR Flash** – pentru memorie suplimentară SPI (64Mbit)

---

### Senzori & Ceas

- **BME688** – măsoară temperatură, umiditate, presiune și gaze (I2C)
- **DS3231** – ceas de timp real, cu precizie ridicată (I2C)

---

### Afișaj

- **E-Paper Driver + Conector**  
  Conectat prin SPI, controlat de ESP32  
  Alimentarea este comutabilă cu un MOSFET (SI1308EDL)

---

### Control și testare

- **Reset / Boot Buttons**
- **Qwiic/Stemma QT Connector** – extensii I2C
- **Test Pads** – debugging ușor

---

### Protecții

- **TVS Diodes**: `PGB1010603MR` – protecție ESD pe linii sensibile
- **Varistori**: protecție la supratensiuni

---

### Conexiuni interfețe

| Interfață | Dispozitive conectate                          |
|-----------|------------------------------------------------|
| I2C       | BME688, DS3231, MAX17048                       |
| SPI       | SD Card, NOR Flash, E-Paper Display            |
| GPIO      | Butoane, LED-uri, Power switches               |



## Estimare Consum Energie


| Componentă                  | Mod activ (mA) | Standby (mA) | Deep sleep (µA) | Observații                                 |
|----------------------------|----------------|--------------|-----------------|--------------------------------------------|
| **ESP32-C6**               | 50–80          | ~2           | ~5              | Wi-Fi consumă cel mai mult                 |
| **BME688**                 | 2.1            | 0.15         | <1              | Măsurare la 1Hz                            |
| **DS3231 (RTC)**           | 0.15           | 0.15         | 0.15            | Activ permanent                            |
| **MAX17048 (Battery Gauge)**| 0.06          | 0.006        | 0.006           | Foarte eficient                            |
| **E-paper Display**        | 5–20           | 0            | 0               | Consumă doar în timpul refresh-ului        |
| **SD Card (scriere activă)**| 30–100        | 0.2          | 0               | Alimentat doar la nevoie                   |
| **W25Q512 (SPI Flash)**    | ~5             | 0.003        | <1              | Are mod standby foarte eficient            |
| **LDO Regulator + pierderi**| 2–5           | 0.5          | 0.2             | Inclus în consum general                   |


---

##  Mapare pini ESP32-C6 

| Pin ESP32-C6 | Componentă                     | Funcție/Interfață     | Motiv / Utilizare                                                                 |
|--------------|-------------------------------|------------------------|-----------------------------------------------------------------------------------|
| **IO0**      | Buton `BOOT`                  | GPIO / Input          | Intrare folosită pentru intrarea în mod bootloader                               |
| **IO1**      | `RTC DS3231`                  | I2C SDA               | Comunicare cu ceasul de timp real                                                |
| **IO2**      | `RTC DS3231`                  | I2C SCL               | Comunicare I2C                                                                    |
| **IO3**      | `BME688`, `MAX17048`          | I2C SDA               | Magistrală I2C partajată cu ceilalți senzori                                     |
| **IO4**      | `BME688`, `MAX17048`          | I2C SCL               |                                                                                   |
| **IO5**      | `W25Q512 NOR Flash`           | SPI CS                | Chip select pentru memoria flash externă                                         |
| **IO6**      | `W25Q512`, `SD Card`, `E-Paper`| SPI CLK               | Comun partajat între toate dispozitivele SPI                                     |
| **IO7**      | `W25Q512`, `SD Card`, `E-Paper`| SPI MISO              | Date de la dispozitive SPI                                                       |
| **IO8**      | `W25Q512`, `SD Card`, `E-Paper`| SPI MOSI              | Date către dispozitivele SPI                                                     |
| **IO9**      | `SD Card`                     | SPI CS                | Selectare card SD                                                                 |
| **IO10**     | `E-Paper`                     | SPI CS                | Selectare afișaj                                                                 |
| **IO11**     | `E-Paper`                     | BUSY / RESET / DC     | Control afișaj e-paper                                                            |
| **IO12**     | `E-Paper`                     | BUSY / RESET / DC     |                                                                                   |
| **IO13**     | `E-Paper`                     | BUSY / RESET / DC     |                                                                                   |
| **IO18**     | Buton `RESET`                 | GPIO / Input          | Reset hardware                                                                    |
| **IO19**     | LED / Control MOSFET-uri      | GPIO / Output         | Power gating sau status LED-uri                                                  |                                                |



## Observații și decizii de design:

- **SPI** este partajat între 3 periferice: SD card, NOR flash, e-paper. Fiecare are propriul pin CS.
- **I2C** este partajat între 3 dispozitive: BME688, DS3231 și MAX17048. Adresele sunt diferite.
- Pinul **IO0** este standard pentru BOOT, iar **IO18** este adesea folosit pentru RESET.
- GPIO suplimentare (ex. IO19, IO20) pot fi folosite pentru controlul alimentării modulelor (e.g., enable pin pe SD/e-paper).
- Se folosesc pinii **de jos (IO0–IO13)** pentru compatibilitate cu bootloader-ul și SPI flash extern.

