# N64 RCP Flex Suite
During my deep-dive into the N64's anatomy, I wanted to come up with a way to simplify rewiring of the cartridgle slot, once the original footprint is trimmed off of the N64 motherboard. I started by making a flex PCB that solders to the RCP on the N64, which leaves only the PIF lines (excluding PIF-6), CPU-57 and Sync to be manually soldered. All connections are run over a 40 pin 0.5mm pitch FFC cable to a receiver board that fits an aftermarket 50-pin cart edge connector. Not much has been done with the design since I proved it works, but I plan on integrating the design (or some offsprint of it) in my own N64 portable. I did scale down the flex to a simple breakout board for manually wiring the RCP lines to the cart connector, mainly to retrofit into builds that require RCP wiring (such as the [N64HHv2](https://bitbuilt.net/forums/index.php?threads/n64hh-v2.6107/) by [Nicholas298](https://bitbuilt.net/forums/index.php?members/nicholas298.4877/).

I created the following document to keep track of the RCP-FFC-Cart connections. An xlsx version is included in the repo as well.

<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/pinout" width=300>

## RCP-FFC
This flex solders directly to the RCP on the N64. The only handwiring required is for PIF-1, PIF-3, PIF-5, PIF-7, PIF-23/24, CPU-57, and Sync (on the video DAC). Keep in mind that multiple PIF pins go to multiple places on the N64 motherboard, not just to the cart slot. As per the [N64 trimming guide](https://bitbuilt.net/forums/index.php?threads/the-advanced-n64-trimming-guide.3992/), those lines need to be wired to *all* of the marked locations.

<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/layout" width=300>\
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/install1" width=300>
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/install2" width=300>
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/install3" width=300>
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/install4" width=300>

I made two receiver PCBs for the replacement 50-pin cartridge slot. One with the FFC facing the *front* of the cartridge (not ideal for integrating into a portable), and one with the FFC facing the *back* of the cartridge (more ideal). I would recommend only using these boards as references, as they were not made with any kind of portable in-mind, and have an incorrect footprint for the cart edge connector.

FFC facing the *front* of the cartridge:

<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/cart-wrong-front" width=300>\
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/cart-wrong-back" width=300>

FFC facing the *back* of the cartridge:

<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/cart-right-front" width=300>\
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/cart-right-back" width=300>

I did not check the row-to-row spacing for the replacement 50-pin connector, so it will not fit into these boards as-is. The pins need to be bent as shown if you want to use these boards.

<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/pin-bend" width=300>

After testing the flex on a stock N64, I tested it and confirmed functionality on a trimmed board.

<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/test1" width=300>
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP-FFC/test2" width=300>

## RCP Breakout Flex
It's an RCP-FFC... without the FFC! It makes RCP wiring a whole lot nicer than soldering right to the IC. It does not include any 3v3 pads, as it can be pulled from a nearby source on the N64.

<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP Breakout Flex/layout.PNG" height=300> <img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP Breakout Flex/install.jpg" height=300>\
<img src="https://github.com/CrazyGadgetMods/N64-RCP-Flex-Suite/blob/main/images/RCP Breakout Flex/test.jpg" height=300>

## Credits
- [YveltalGriffin](https://github.com/mackieks): Answering my million questions and proving tips for designing flexes
- [Gman](https://github.com/Gmanmodz): Helping me learn the N64's anatomy
- [SparkleBear](https://bitbuilt.net/forums/index.php?members/sparklebear.6753/): Getting me into the N64
- [BitBuilt](https://bitbuilt.net/): Being the best modding community out there!

## License
Solderpad Hardware License v2.1
