<div align="center">
  <img style="margin: auto; width: 500px" src="https://github.com/user-attachments/assets/754f7860-e2d3-4e09-b584-bd55c48fb215"/>
</div>

<p>
  
This is a breakout pcb for the commonly used AS5047P magnetic position sensor IC. Its SPI communication protocols are supported by many motor drivers such as VESCs and ODrives (newer ODrives have them built in, but boards based on the older open source designs like the ODesc don't). I designed this in KiCad, so if you want to work on it you'll need to install that.

It's also designed to mount easily with generic 360kv 5010 brushless motors like [these](https://speedyfpv.com/collections/brushless-motors/products/5010-brushless-motor-360kv-2-6s-high-torque-motor-for-14-18-props?variant=42912725860566). The mounting hole placement is sketched in an image below. There are two sets of holes, the wider set are 19mm apart and the closer set are 16mm apart.

This board exposes all possible communication interfaces with the IC:
- SPI
- ABI
- UVW
- PWM

Although it should be noted that some of these modes may require additional configuration over SPI to work (I believe the UVW mode needs to know the number of poles on the motor to function properly). Refer to the [datsheet](https://look.ams-osram.com/m/d05ee39221f9857/original/AS5047P-DS000324.pdf) for more information.

This board allows for either 3.3 or 5 volt operation through a solder jumper on the back side, and all of the connectors are JST GH (kits for these are easily available on amazon).

These are super easy to get manufactured, I use JLC PCB, the gerbers, bom, and pcl files are all included in this repo. Just upload `gerber_old.zip` (it's marked as old but that's because I had to mess with the mirroring on the back silkscreen to get everything to print correctly from the fab, this file is the one that works) to JLC. Next, select the assembly option, the bom and cpl files are in the `placement` directory.

JLC stocks all the components needed for this board and the bom is set up to automatically pull the correct ones from their catalog. You will have to rotate the AS5047P IC in the placement confirmation window (make the pink dot line up with the arrow on the silk screen on the board), this should just be a 90 degree rotation, nothing crazy. Hopefully I will come back and fix the placement to eliminate this issue later.

When it's all said and done, these cost me about $10 per board with shipping and tarrifs included (I live in the US). If you choose the cheaper shipping option and don't have to deal with crazy tarrifs, then these could get down closer to $7 per board, which is a fantastic deal. Especially considering that similar encoders like the AS5048A on amazon cost closer to $14 per board (at least at the time of writing).

If you find a mistake, or want to make an improvement, feel free to open a pr!

Mounting hole spacing, the holes are M3.
</p>
<div align="center">
  <img style="width: 500px" alt="Screenshot 2025-07-25 at 11 12 52 PM" src="https://github.com/user-attachments/assets/f4e9ef46-88ad-4f56-8068-89c26f3c31aa" />
</div>
