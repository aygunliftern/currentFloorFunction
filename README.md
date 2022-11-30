# Contents

1. Normal Mode
2. Calibration Mode

# Normal Mode

This part includes conditions after system found it's first floor in Calibration Mode.

If carCurrentFloor is not 0 then, following conditions checked:
- If elevator is in doorzone
- If elevator is not in doorzone and 142 signal is TRUE and inspection up signal (inspectionUpNew) is TRUE or moving up signal (movingUpNew) is TRUE and current floor is less than total floor,
	 - Increment carCurrentFloor.
- If elevator is not in doorzone and 141 signal is TRUE and inspection down signal (inspectionUpNew) is TRUE or moving down signal (movingUpNew) is TRUE and current floor is bigger than first floor,
	- Decrement carCurrentFloor.

