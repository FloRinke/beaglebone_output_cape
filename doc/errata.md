# Errata
## Revision 1.0
Several outputs collide with internally used pins
- CH05: GPIO03_21 	(HDMI Clock, optional) -> GPIO03_17
- CH01: GPIO1_2 	(eMMC)
- CH16: GPIO1_6 	(eMMC)
- CH13: GPIO1_31 	(eMMC) -> GPIO02_1
- CH12: GPIO1_0 	(eMMC) -> EHRPWM2A
- CH11: GPIO2_23 	(HDMI, optional) -> GPIO01_29
- CH10: GPIO2_12 	(HDMI, optional)
- CH09: GPIO2_10 	(HDMI, optional)
- CH07: GPIO2_8 	(HDMI, optional)

# Changelog
## Rev 1.1
Reorder GPIO-Assignment to solve collisions
## Rev 1.0
Initial Revision