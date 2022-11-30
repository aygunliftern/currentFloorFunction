# Contents

1. Normal Mode
2. Calibration Mode

## Normal Mode

This part includes conditions after system found it's first floor in Calibration Mode.

Normal Mode has 3 part of conditions:
1. Elevator is in Doorzone
2. Elevator is not in Doorzone
3. Elevator is on Limits

##### Elevator is in Doorzone

If carCurrentFloor is not 0 then, following conditions checked:
- If carCurrentFloor is bigger than 0
	- enableUpdateUp is TRUE
	- enableUpdateDown is TRUE
##### Elevator is not in Doorzone
- If elevator is not in doorzone and 142 signal is TRUE and inspection up signal (inspectionUpNew) is TRUE or moving up signal (movingUpNew) is TRUE and enableUpdateUp is TRUE and current floor is less than total floor,
	 - Increment carCurrentFloor.
	 - enableUpdateUp is FALSE
- If elevator is not in doorzone and 141 signal is TRUE and inspection down signal (inspectionUpNew) is TRUE or moving down signal (movingUpNew) is TRUE and enableUpdateDown is TRUE and current floor is bigger than first floor,
	- Decrement carCurrentFloor.
	- enableUpdateDown is FALSE
##### Elevator is on Limits
- If 818 is FALSE and 817 is TRUE,
	- carCurrentFloor is equal to total number of floors.
- If 818 is TRUE and 817 is FALSE,
	- carcurrentFloor is equal to 1.

