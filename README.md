# Humanoid-Robot-Walking-Motion-Algorithm

## Input Parameters:
- Leg length: Distance from hip to ankle.
- Step length: Horizontal distance the robot should move with each step.
- Stride height: Vertical height of the foot during each step (to avoid obstacles).
- Walking speed: Time between each step to control how fast the robot walks.
- Balance assumption: Predefined balance model based on leg length, stride height, and step length.

### 1. Initialize System:
- Activate all actuators (servos in each leg).
- Set the robot’s initial position with both feet flat on the ground.
- Set the robot’s body position (upright stance).
- Predefine the walking gait pattern (steps per second, step length, and stride height).

### 2. Walking Loop (Cycle for Each Step):
For each cycle (two steps, one for each leg), perform the following steps:

Cycle Iteration:

  Step 2.1: Lift the Left Leg (Swing Phase):
  - Lift the left leg by moving the hip joint to raise the thigh.
  - Bend the knee to lift the foot off the ground.
  - Move the leg forward in a smooth motion (set predefined horizontal and vertical movement).
  - As the leg moves forward, raise the foot to a set stride height (vertical).
  - Continue until the foot is placed ahead of the body in the air.
  
  Step 2.2: Place the Left Foot on the Ground (Stance Phase):
  - Once the left foot reaches the desired position ahead of the body, slowly lower it to the ground.
  - Ensure that the foot lands flat on the ground, and adjust the ankle joint to maintain a stable foot placement.
  - Shift the robot’s body weight to the left leg.
  - Slightly bend the knee of the left leg to absorb the body weight and provide stability.
  
  Step 2.3: Shift the Body’s Weight (Balance Adjustment):
  - As the left leg is now planted on the ground, shift the body weight onto the left leg.
  - Ensure the right leg is still in the swing phase.
  - The body remains balanced by keeping the torso upright.
  
  Step 2.4: Lift the Right Leg (Swing Phase):
  - While the body weight is on the left leg, lift the right leg by raising the hip joint and bending the knee.
  - Move the right leg forward in a smooth motion, following the predefined path.
  - Raise the foot to the desired stride height.
  - Bring the foot forward, preparing for placement ahead of the body.
  
  Step 2.5: Place the Right Foot on the Ground (Stance Phase):
  - As the right foot reaches the desired position, lower it to the ground.
  - Ensure the right foot lands flat and adjust the ankle if needed to maintain balance.
  - Shift the body weight to the right leg.
  - Slightly bend the right knee to absorb the weight and maintain a stable stance.
  
  Step 2.6: Repeat the Cycle:
  - Continue alternating between the left and right legs, performing steps 2.1 through 2.5 until the desired walking distance or time is achieved.

### 3. Predefined Timing:
  - Walking Speed: Control the walking speed by adjusting the time delay between steps. For example:
  - Slow walking: Increase the delay (longer step duration).
  - Fast walking: Decrease the delay (shorter step duration).
  - Each leg moves in a set pattern (e.g., left leg first, right leg second), and the time between the swing and stance phases must be consistent to maintain a smooth gait.
    
### 4. Stop Walking:
- To stop walking, slow down the walking cycle by reducing the step length and frequency of movement (increase the delay between steps).
- Bring both feet flat to the ground, adjust the knees to stabilize, and return the robot to an upright standing position.

  
## Walking Pattern Example:
### Step 1: 
- Lift the left leg (Swing phase).
- Move it forward and place it on the ground (Stance phase).
### Step 2:
- Shift the weight onto the left leg.
- Lift the right leg (Swing phase).
- Move it forward and place it on the ground (Stance phase).
### Repeat Steps 1 and 2 to continue walking in a loop.

## Balance Assumption and Staggered Motion:
- The robot’s balance is maintained using a pre-programmed staggered motion. The legs alternate in a predefined sequence, with the weight shifting to the planted leg after each footstep.
- Hip, knee, and ankle movements are carefully timed so that each leg provides support before the other leg moves.
