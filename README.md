  Big thanks to [PCBWay](https://www.pcbway.com/) for sponsoring this project! Their support enables me (and hundreds of other designers) to make cool stuff. More info in [Manufacturing](#manufacturing)
<div align="center">
  <!-- <img style="margin: auto; width: 500px" src="https://github.com/user-attachments/assets/754f7860-e2d3-4e09-b584-bd55c48fb215"/> -->
  <img style="margin: auto; width: 500px" src="images/Encoder Board V2 Image.png"/>
</div>

<p>
This is a breakout pcb for the commonly used AS5047P magnetic position sensor IC. Its SPI communication protocols are supported by many motor drivers such as VESCs and ODrives (newer ODrives have them built in, but boards based on the older open source designs like the ODesc don't). I designed this in KiCad, so if you want to work on it you'll need to install that.

It's also designed to mount easily with generic 360kv 5010 brushless motors like [these](https://speedyfpv.com/collections/brushless-motors/products/5010-brushless-motor-360kv-2-6s-high-torque-motor-for-14-18-props?variant=42912725860566). The mounting hole placement is sketched in an image below. There are two sets of holes, the wider set are 19mm apart and the closer set are 16mm apart.

This board exposes all possible communication interfaces with the IC:
- SPI
- ABI
- UVW
- PWM

Although it should be noted that some of these modes may require additional configuration over SPI to work (I believe the UVW mode needs to know the number of poles on the motor to function properly). Refer to the [datasheet](https://look.ams-osram.com/m/d05ee39221f9857/original/AS5047P-DS000324.pdf) for more information.

This board allows for either 3.3 or 5 volt operation through a solder jumper on the back side, and all of the connectors are JST GH (kits for these are easily available on amazon).

## Manufacturing
All of the files needed to manufacture these boards are provided in the `fabrication` folder.

The process is super easy if you use PCBWay:
1. Upload the `gerber.zip` file to their [instant quote tool](https://www.pcbway.com/QuickOrderOnline.aspx)
    * The default quantity is 5pcs, if you want more, change that here
    * This is a great opportunity to pick a specific color if you want something other than green
    * You may also want to select the `HASL lead free` option rather than the default leaded one
2. You can get bare boards, but assembling them yourself can be a pain. Fortunately, PCBWay can assemble them for you!
    1. Check the `Assembly Service` box. The default options are fine here, make sure to set the quantity of boards you want assembled.
    2. You can now hit the `Save to Cart` button on the right hand side of the screen.
    3. You'll be taken to the orders page, where you'll have to upload a couple more files.
    4. Hit the `Add File` button and upload the `Bom.csv` and `Centroid.csv` files
    5. Now the engineers at PCBWay have to review the order to ensure that everything is correct
    6. Once this process is compete, you can check out, and production will start

PCBWay's amazing customer service team will email you with updates and to check things like component placement throughout the process. But, these boards are fairly simple and there should be no issues here. You can also check the exact status of your order at any time on the website.

> ✅ Results
> 
> I may be biased, but I've found that PCBWay is easily the best way to get PCBs made. The quality of the silkscreen and accuracy of component placement are great. And, the constant updates & communications from the PCBWay team give me great confidence that my projects will succeed on the first try.
>
> I highly recommend their services. And, by supporting them, you support small projects and independent designers like myself!
<hr>

When it's all said and done, these cost me about $10 per board with shipping and tariffs included (I live in the US). If you choose the cheaper shipping option and don't have to deal with crazy tariffs, then these could get down closer to $7 per board, which is a fantastic deal. Especially considering that similar encoders like the AS5048A on amazon cost closer to $14 per board (at least at the time of writing).

If you find a mistake, or want to make an improvement, feel free to open a pr!

Mounting hole spacing, the holes are M3.
</p>
<div align="center">
  <img style="width: 500px" alt="Screenshot 2025-07-25 at 11 12 52 PM" src="https://github.com/user-attachments/assets/f4e9ef46-88ad-4f56-8068-89c26f3c31aa" />
</div>
