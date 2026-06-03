# diagrams
![[Pasted image 20260602172533.png]]

# code examples from the interweb
### tank drive (??)
```
int left = Controller.Axis3.position(vex::percent);
int right = Controller.Axis2.position(vex::percent);
int sideways = Controller.Axis4.position(vex::percent);

//you can also calculate this...
int turn =    (right - left) * 0.5;
int forward = (right + left) * 0.5;

frontRight.spin(vex::forward, right - sideways, vex::percent);
frontLeft.spin(vex::forward,  left  + sideways, vex::percent);
backRight.spin(vex::forward,  right + sideways, vex::percent);
backLeft.spin(vex::forward,   left  - sideways, vex::percent);

```
### arcade drive
```
int forward = Controller.Axis3.position(vex::percent);
int sideways = Controller.Axis4.position(vex::percent);
int turn = Controller.Axis1.position(vex::percent);

frontRight.spin(vex::forward, forward - sideways + turn, vex::percent);
frontLeft.spin(vex::forward,  forward + sideways - turn, vex::percent);
backRight.spin(vex::forward,  forward + sideways + turn, vex::percent);
backLeft.spin(vex::forward,   forward - sideways - turn, vex::percent);
```

# what we need to do:
### input expectations:
##### sticks:
rightStick:
- vertical: forward/backward movement
- horizontal: left/right movement
leftStick:
- vertical: nothing?
- horizontal: rotate bot
#### other:
nothing for now

### the math idk

#### motor axis calculations:
```
rightFrontWheelSpin = forward - sideways + turn
rightRearWheelSpin = forward + sideways - turn
leftFrontWheelSpin = forward + sideways + turn
leftRearWheelSpin = forward - sideways - turn
```

![[Pasted image 20260602182011.png]]