# Contents

1. [Normal Mode](#normal-mode)
2. [Calibration Mode](#calibration-mode)

## Normal Mode

This part includes conditions after system found it's first floor in Calibration Mode.

Normal Mode has 3 part of conditions:
1. [Elevator is in Doorzone](#elevator-is-in-doorzone)
2. [Elevator is not in Doorzone](#elevator-is-not-in-doorzone)
3. [Elevator is on Limits](#elevator-is-on-limits)

#### Elevator is in Doorzone
If carCurrentFloor is not 0 then, following conditions checked:
- If carCurrentFloor is bigger than 0
	- enableUpdateUp is [TRUE](#true)
	- enableUpdateDown is [TRUE](#true)

#### Elevator is not in Doorzone
- If elevator is not in doorzone and 142 signal is [TRUE](#true) and inspection up signal (inspectionUpNew) is [TRUE](#true) or moving up signal (movingUpNew) is [TRUE](#true) and enableUpdateUp is [TRUE](#true) and current floor is less than total floor,
	 - Increment carCurrentFloor.
	 - enableUpdateUp is [FALSE](#false)
- If elevator is not in doorzone and 141 signal is [TRUE](#true) and inspection down signal (inspectionDownNew) is TRUE or moving down signal (movingDownNew) is [TRUE](#true) and enableUpdateDown is [TRUE](#true) and current floor is bigger than first floor,
	- Decrement carCurrentFloor.
	- enableUpdateDown is [FALSE](#false)

#### Elevator is on Limits
- If 818 is FALSE and 817 is [TRUE](#true),
	- carCurrentFloor is equal to total number of floors.
- If 818 is TRUE and 817 is [FALSE](#false),
	- carcurrentFloor is equal to 1.

## Calibration Mode

This part include finding first floor of the elevator.

- If ML1 signal (iML1) is [TRUE](#true) and ML2 signal (iML2) is [TRUE](#true) and 141 signal (iSignal141) is [TRUE](#true) and 142 signal (iSignal142) is [TRUE](#true),
	- carCurrentFloor equal to 1.

# Abbreviations

 ##### **FALSE** 
 > means it is 0
 ##### **TRUE**
 > means it is 1
