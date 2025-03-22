

# Setup:
- base on "3dprint-ender3-marlin\marlin-configurations\config\examples\Creality\Ender-3\CrealityV427\"
- copy the "./Marlin" directory to "../marlin-firmware/Marlin" and overwrite existing configuration
  
# Related links
  https://web.archive.org/web/20230111012211/https://printermods.co.uk/blogs/guides/creality-v4-2-2-v4-2-7-motherboard-stepper-driver-codes?fbclid=IwAR2qpePD5FNIq2MnVJgaDQKTz58oK01V-_VONsOBi7La7Mo_z0pFeRhaaK8
  The letters hand written on the card reader slot.
  V4.2.7 boards with the STM32F103RET6 micro controller:
- C = HR4988
- E = A4988
- A = TMC2208
- B = TMC2209
- H = TMC2225  => this is my configuration
- T5 = TMC2225
- T8 = TMC2208
Note: In Marlin firmware use TMC2208_STANDALONE for TMC2225 drivers (H)  