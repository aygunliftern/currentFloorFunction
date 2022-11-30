# Contents

1. Normal Mode
2. Calibration Mode

# Normal Mode

This part includes conditions after system found it's first floor in Calibration Mode.

If carCurrentFloor is not 0 then, following conditions checked:
- If elevator is in doorzone
- If elevator is not in doorzone and 142 signal is 1 and inspection up signal (inspectionUpNew) is TRUE or moving up signal (movingUpNew) is TRUE,
	 - counterstatus_brcactive set to [STATE_SET](#state_set)
- dsd
