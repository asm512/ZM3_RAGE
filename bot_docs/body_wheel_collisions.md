vehicle_tire, tire shader, rim shader, wheel shader, vehicle tire

Every object contained under `wheel_lf` or any other wheel **must** be assigned to the `vehicle_tire` shader.
The `vehicle_tire` shader does not support alpha, and therefore transparent textures will not work.
Tire dirt values are always 10-15% more than the rest of the vehicle unless the vehicle dirt level is 0%.