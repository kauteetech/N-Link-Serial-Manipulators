# 3D Serial Manipulator Web App

## Description

This application simulates an N-link serial manipulator in a 3D environment. Users can dynamically change the number of links, control the rotation of each joint, and operate a gripper to pick and place a target object. The application also calculates and displays the real-time 3D coordinates and orientation of the manipulator's components.

## Features

* **Dynamic Link Configuration:** Adjust the number of links (1 to 4) on the fly.

* **Joint Control:** Individual sliders for base rotation and each joint's angle.

* **Interactive Gripper:** Control the opening and closing of the end effector gripper.

* **Pick and Place:** Logic to "hold" and "release" a target object when the gripper is closed and positioned correctly.

* **Target Object Control:** Manually set or randomize the position of a target sphere.

* **Floor Collision Alarm:** A visual alert pops up if the end effector touches the floor.

* **Gripper Hold Confirmation:** A green alert confirms when the gripper has successfully grabbed the object.

* **Forward Kinematics Display:** Real-time table showing X, Y, Z coordinates and end effector orientation.

* **3D Visualization:** Elegant 3D rendering with curved links, joints, and realistic shadows.

* **Camera Control:** Orbit the camera around the manipulator using your mouse.

## How to Use

1.  **Access the Application:**

    * Save the provided HTML code as an `.html` file (e.g., `index.html`).

    * Open this HTML file in a modern web browser (e.g., Chrome, Firefox, Edge).

2.  **Manipulator Simulation (Left Panel):**

    * This is the main 3D view of your serial manipulator.

    * **Camera Control:** Click and drag your mouse on the canvas to rotate the camera around the manipulator. Use the scroll wheel to zoom in and out.

3.  **Manipulator Controls (Right Panel):**

    * ### Configuration:

        * **Number of Joints:** Use the slider to increase or decrease the number of links (from 1 to 4). The manipulator will rebuild immediately.

    * ### Base Control:

        * **Base Rotation (θ₀):** Adjust this slider to rotate the entire manipulator around its vertical axis (yaw).

    * ### Joint Angles (Elbows):

        * Sliders for each joint (θ₁, θ₂, etc.) will appear dynamically based on the "Number of Joints" selected.

        * Adjust these sliders to control the bending angle of each "elbow" joint. Note that the angles are constrained (0° to 135°) to prevent the arms from going below the floor.

    * ### End Effector (Gripper):

        * **Gripper Opening:** Use this slider to open and close the gripper.

            * Moving the slider towards `0` (0%) will close the gripper.

            * Moving the slider towards `1` (100%) will open the gripper.

    * ### Target Object:

        * **Target X, Y, Z:** Use these sliders to manually position the red target sphere in the 3D space.

        * **Random Target:** Click this button to place the target object at a random position just above the floor.

4.  **Picking and Placing an Object:**

    * Adjust the Base Rotation and Joint Angles to position the gripper directly over the red target sphere.

    * Slowly close the gripper using the "Gripper Opening" slider.

    * If the gripper is sufficiently closed and close enough to the object, a **"Gripper Holding Object!"** green alert will appear.

    * Once the object is held, the "Target Object" sliders will be disabled, as the object's position is now controlled by the manipulator.

    * Move the manipulator to a new desired location.

    * Open the gripper using the "Gripper Opening" slider. The **"Gripper Holding Object!"** alert will disappear, and the object will be released at its current position. The "Target Object" sliders will re-enable.

5.  **Dynamic Calculations (Forward Kinematics) - Bottom Section:**

    * **Joint Coordinates Table:** This table automatically updates to show the global X, Y, and Z coordinates of the base, each joint, and the end effector in real-time.

    * **End Effector Orientation:** Displays the Roll, Pitch, and Yaw angles of the end effector, indicating its orientation in 3D space.

## Important Notes:

* The arm segments are designed with a minimum joint angle of 0 degrees to prevent them from intersecting the floor.

* The "End Effector Touches Floor!" alarm will activate if the lowest point of the gripper goes below a certain threshold.

* The pick-and-place mechanism relies on proximity and gripper closure. Ensure the gripper is directly over and close to the object when closing it.
