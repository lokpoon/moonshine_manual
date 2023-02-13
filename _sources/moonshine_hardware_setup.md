---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# <span style="font-variant:small-caps;">MoonShine</span>: Hardware setup
(content:hardware:materials)=
## Materials

| Item  | SKU/model number | Company  | Quantity required | Price | Link   | Note |
|-------|------------------|----------|-------------------|-------|--------|------|
| Raspberry Pi 4 model B kit | XXX | GeeekPi | 1 | $200 | [Amazon](https://www.amazon.com/GeeekPi-Raspberry-2GB-Starter-Kit/dp/B0B7DFF7TY/ref=sr_1_5?crid=1BQNGTSE4SSDJ&keywords=raspberry+pi+4+kit&qid=1674623289&sprefix=raspberry+pi+4+kit%2Caps%2C121&sr=8-5&ufe=app_do%3Aamzn1.fos.f5122f16-c3e8-4386-bf32-63e904010ad0) | [^1] |
| RTC module (DS3231) | 3-01-1198 | HiLetgo | 1 | $ | [Amazon](https://www.amazon.com/HiLetgo-DS3231-Precision-Arduino-Raspberry/dp/B01N1LZSK3/ref=sr_1_2?crid=33U6N5U6HSRWK&keywords=rtc+ds+3231&qid=1674685955&sprefix=rtc+ds+3231%2Caps%2C72&sr=8-2) | - |
| Generic mouse and keyboard | - | - | 1 | ~40 | - | - |
| Generic HDMI monitor | - | - | 1 | ~$100 | - | - |
| SK6812 RGBW LED strip | SK68121M144-RGBWWW65 | BTF-Lighting | At least 2 | $35 | [Amazon](https://www.amazon.com/BTF-LIGHTING-Individually-Addressable-Flexible-Waterproof/dp/B01N2PCIB9/ref=sr_1_6?crid=3OWYKHJC7QV57&keywords=sk6812%2Bwarm&qid=1674596692&sprefix=sk6812%2Bwarm%2Caps%2C104&sr=8-6&th=1) | [^2] |
| 2.54mm pitch crimp connector kit | XXX | OCR | 1 | $12 |[ Amazon ](https://www.amazon.com/OCR-Connector-Housing-Assortment-640Pcs-Set/dp/B071JLCFT6/ref=sr_1_15?crid=1RCAOTD9CWZTD&keywords=gpio+connector+kit&qid=1674669821&sprefix=gpio+connector+kit%2Caps%2C91&sr=8-15)| - |
| 3-pin extension cable (pack of 2m x 4) | HL-LED79 | Hualand | At least 1 | $12 |[ Amazon ](https://www.amazon.com/Connector-WS2812B-Symphony-connectors%EF%BC%8CSM3P-controller/dp/B07G6PRDBQ/ref=sr_1_11?keywords=jst+3+pin+connector&qid=1674670291&sprefix=JST+3+pin+conn%2Caps%2C105&sr=8-11)| [^3] |
| 3 conductor wire 100ft | AT-3P-100FT | AOTOINK | 1 | $16 | [Amazon](https://www.amazon.com/AOTOINK-Extension-Electrical-Stranded-Lighting/dp/B08JTZKN4M/?crid=2MQUPBVHO898U&sprefix=3+core+wir,aps,104) | - |
| 5V10A DC power adapter | P5V10A | BTF-Lighting | One per LED strip | $22 |[ Amazon ](https://www.amazon.com/BTF-LIGHTING-Plastic-Adapter-Transformer-WS2812B/dp/B01D8FM71S?ref_=ast_sto_dp&th=1)| - |
| Lumber boards | - | Home Depot | One set per LED strip | $17 | - | [^4] |
| Generic black spray paint | - | - | 1 | $6 | - | - |
| Neutral Density (ND) filter sheets | - | Lee Filters | Depends | ~$20 per diffusion box | [BarnDoor](https://www.filmandvideolighting.com/lee-neutral-denisty-nd-gel-filter-sheet-film-video-photo-lighting.html) | [^5] |
| Lux meter/radiometer/spectrometer | - | - | 1 | $200 to >5000 | - | [^6] |
| UPS backup battery power | BE425M | APC | 1 | $60 | [Amazon](https://www.amazon.com/APC-Battery-Protector-Back-UPS-BE425M/dp/B01HDC236Q/ref=sr_1_7?keywords=uninterruptible%2Bpower%2Bsupply&qid=1674685859&sprefix=uninter%2Caps%2C105&sr=8-7&ufe=app_do%3Aamzn1.fos.006c50ae-5d4c-4777-9bc0-4513d670b6bc&th=1) | - |
|  |  |  |  | $ |  |  |
|  |  |  |  | $ |  |  |
```{note}
Estimated total cost for one MoonShine system (excluding the illuminance measuring device) = $653 (Jan 2023)
```

### Tools
- Wire stripper (for small gauge wire ~22-26 AWG)
- Needle pliers
- Wood hand saw
- Driver

### Basic supplies
- Wood screws
- Masking tape
- Foam pieces

[^1]: Any equivalent kit of the Raspberry Pi 4 model B from other companies would work. Beside the Pi itself, the kit should include all the accessories such as HDMI cable, power supply, case, SD card, etc. _<span style="font-variant:small-caps;">MoonShine</span>_ only requires the 2GB RAM option, but there is the option for more RAM (4GB or 8GB).
    
    At the time of writing this document, price of Pi is much higher than the official price due to supply issues.

[^2]: We recommend the following options: **1m, 144 LED, Warm White**. There is also the option for a IP65 water resistant or IP30 normal version, choose whichever one is more suitable for the user's application. Choose warm white because we do not want the big blue spike in the white channel spectrum. A different strip length and LED number can be selected, but we believe 1m 144 LED is the best suited for most situations.

    Two LED strips are required for moonlight recreation. More can be added in multiple of two to daisy chain many more strips, e.g., when trying to recreate a higher illuminance when recreating sunlight.

[^3]: Buy enough connector cable for daisy chaining LED strips around the user's room.

[^4]: The dimensions lumber boards for building one diffusion box:
    - Base: One of 5/4" x 6" x 4' [home depot](https://www.homedepot.com/p/WeatherShield-5-4-in-x-6-in-x-4-ft-Premium-Ground-Contact-Pressure-Treated-Decking-Board-253944/300526781) ($6)
    - Two Sides: Two of 1" x 4" x 4' [home depot](https://www.homedepot.com/p/WeatherShield-1-in-x-4-in-x-4-ft-Appearance-Grade-Pressure-Treated-Board-275086/300573653) ($7.4)
    - End caps: Cut down a 1" x 4" x 4' [home depot](https://www.homedepot.com/p/WeatherShield-1-in-x-4-in-x-4-ft-Appearance-Grade-Pressure-Treated-Board-275086/300573653) ($3.7)

[^5]: The ND filter required depends on the user's room and setup. It should take two or three filters per diffusion box to dim the lightbox. See {ref}`content:lightbox:calibration` to learn which ND intensity to try out.
    
    Lee ND filter sheet lineup:
    - Lee 298 (ND 0.15, ½ Stop) = Transmission 69.3%
    - Lee 209 (ND 0.3, 1 Stop) = Transmission 51.2%
    - Lee 210 (ND 0.6, 2 Stop) = Transmission 23.5%
    - Lee 211 (ND 0.9, 3 Stop) = Transmission 13.7%
    - Lee 299 (ND 1.2, 4 Stop) = Transmission 6.6%
    
    Rosco is another company that makes ND filter sheets.

[^6]: "Lux meter" is just a commercial term for radiometer, both measure illuminance in lx. We need to measure the illuminance to calibrate Moonshine. Spectrometer is like an upgraded radiometer. It measures spectral irradiance, which provides spectral information about the light. Meanwhile, spectral irradiance measurements can easily be converted into illuminance. However, spectrometers generally carries high cost.
    
    An accurate illuminance measuring device is critical for calibrating Moonshine, but ones that measures at low light are very expensive. We do not want the cost of the radiometer to discourage the use of Moonshine for moonlight related experiments. Still, it is critical to obtain a meter that has NIST-Traceable calibration, like this [ILT10C](https://www.intl-lighttech.com/products/ilt10c-luxlight-meter-nist-traceable-calibration?gclid=Cj0KCQiAw8OeBhCeARIsAGxWtUzB0YaQDpYF5fXMYee-U9zSQgnbmph4LrlmD0inkbSdw4FtaJ-AjjsaApwYEALw_wcB). Lower cost meters can not measure at moonlight level illuminance (i.e., >0.3lux), still we can calibrate Moonshine through a comparative method. See further explanations and solutions in {ref}`(content:lightbox:radiometer`
    
    For us, we use the International Light Technology [ILT-5000](https://www.intl-lighttech.com/products/ilt5000-researchlab-radiometer) radiometer, with a SUD100/U detector equipped with Y4 photopic filter (total ~$4000).

(content:hardware:assemble)=
## Assemble Pi and LED strips
```{figure} /images/raspberry-pi.png
:name: schematic

Connection diagram for the Pi, RTC module, and LED strips. The solid color circles (red, white, green) indicate the PINs connected to the first array of LED strips for moonlight recreation. The open color circles are connected the second array of LED strips, for simultaneous recreation of sunlight and twilight. Wire color schematic according to SK6812 made by BTF-Lighting, Guangdong, China.  
```
```{figure} /images/cable.png
:name: cable

Photo of the actual connection for one array of LED strips. Click the figure to zoom in.
```

1. Follow the Raspberry Pi kit assembly instruction.
2. On one end of the 3-pin cable female connector (comes with the LED strip), put on a female crimp connector. See [this guide](https://www.youtube.com/watch?v=JsoqBS1-k7M) for installing crimp pins with needle nose pliers.
    - Follow {numref}`schematic` (solid color circles) for the first array of LED strips. When Pi is oriented so that the GPIO are facing up and on the right side,the crimp connected is plugged into the upper right corner of the GPIO array.
        - Red wire goes into the 5V PIN.
        - White wire goes into the ground PIN.
        - Green wire goes into the GPIO 18 data PIN.
4. Plug female crimp connector into the Pi PINs so that the wires are connected to the correct locations.
5. On the other end of the 3-pin cable with the female quick release socket, connect it to the male plug of the LED strip. (Add an extension cable if more length is required).
6. Connect the female connector to the LED strip male connector. Notice the arrows on the LED strip, this indicated the direction of the data flow (from Pi to the array of LED strips).
7. Screw in the LED voltage-adding wires (red-positive and white-negative) to the power female connector (comes with the DC power supply). Pay attention to the polarity.
8. Plug in DC power supply.
9. Connect additional LED strips to this array from the other end (away from the Pi) of the first LED strip. Add additional DC power supply on subsequent LED strips.
10. Install the RTC module as shown in {numref}`schematic` & {numref}`cable`, so that it is on the same end of the crimp connector and next to it. 
11. (Optional) To add a second array of LED strips for recreating sunlight and twilight, while running moonlight recreation, follow {numref}`schematic` (open color circles) for PIN connections.
12. (Optional) To prevent power surge and outage event interrupting the light schedule, connect all power to a uninterrupted power supply (UPS).

## Construction of diffusion box
- Make a diffusion box for each of the two LED strips used for moonlight recreation.

```{figure} /images/diffusion_box.png
:name: box

Construction of a diffusion box housing one LED strip.
```
1. Construct the wooden box as {numref}`box` with screws. With:
    - 5/4" x 6" x 4' board as the base.
    - A 1" x 4" x 4' board on each long side.
    - Cut down a 1" x 4" x 4' to get two end caps.
2. Spray paint the interior in black.
3. Install the LED strip on the center bottom of the lightbox. The bottom of the LED strip should comes with sticky tape.
4. Drill a small hole on each end of the box for the cables. Plug it with small pieces of foam to prevent light leak.
5. Cut ND filter sheets into the correct size, and secure them on the top opening with masking tape. Ensure no light leak. See {ref}`content:lightbox:calibration` regarding how many ND filter sheets to use.