# Video Timing Board
A Development board to extract timing and subcarrier signals from a composite PAL or NTSC video source.

This is part of my ongoing project to develop a system to superimpose colour text and graphics from a microcontroller onto a composite TV signal. My earlier experimenter's board which can be found at https://github.com/Batperson/video_experimenters_board used a high-speed digital decoder and encoder connected back-to-back, but I now want to try some different methods.

One method is to use an AD724 chip from Analog Devices to generate composite video from RGB signals supplied by a microcontroller. If the AD724 is driven by a clock synchronised with an incoming video signal's colour subcarrier, then its output will also be synchronised with that same subcarrier (i.e. genlocked). Then, a fast switch can be used to switch between the incoming video signal and the text/graphic video signal which we wish to superimpose.

Another method is to generate composite video directly from a microcontroller using the SPI output. Rossum at https://rossumblog.com/2010/06/10/rbox-a-diy-32-bit-game-console-for-the-price-of-a-latte/ has already demonstrated this with the most impressive RBox, a game console based on the Arm Cortex M0 which generates full-colour composite video without any supporting ICs. My theory is that I can do the same, but supply an external clock to the SPI. If this clock is derived from an incoming video signal's colourburst then the output should be genlocked..
