# Practice projects

## Hand-controlled camera in VR

### Task 1 (Mar 2)

- Install Unity 2022, install Ultraleap 3Di SDK [software](https://www.ultraleap.com/downloads/)
	- Date: 2.3.26
	- What I did: Installed Unity 2022.3.17f1, downloaded and installed the Ultraleap 3Di SDK.
	- Issues: None

- Create empty VR project
  	- Date: 3.3.26
	- What I did: I created a Unity VR project called “Hand‑controlled Camera in VR.”
	- Issues: None

- Add Ultraleap package as described [here]( https://docs.ultraleap.com/xr-and-tabletop/xr/unity/getting-started/index.html)
  	- Date: 3.3.26
  	- What I did: I went to Project Settings → Package Manager and entered the Name, URL, and Scope.
	Then, in the Window menu, I installed Ultraleap Tracking and imported the Tabletop Examples from the Samples section.
	After that, in Project Settings → XR Plug‑in Management → OpenXR, I enabled Ultraleap Hand Tracking.
  	- Issues: The first time, I installed several other unnecessary items in the Window section, so it didn’t work. That’s why I created the project again the second time, and then it worked.

- Open the "Tabletop Example" project from the package's "Samples" section
 	- Date: 3.3.26
    - Done
- Compile and run the project, and ensure the virtual hands are reflecting hand movements.
  	- Date: 3.3.26
	- The hands are displayed in Unity in real time: https://drive.google.com/file/d/1Y_gJpbP6QvHLoNCBNTestix89OaoeZtd/view?usp=sharing

- Follow [the instructions](https://docs.ultraleap.com/xr-and-tabletop/xr/unity/getting-started/your-first-project.html) to add hand rigs to you own project.

- Study [Ultraleap Plugin features](https://docs.ultraleap.com/xr-and-tabletop/xr/unity/plugin/index.html) to learns hand tracking capabilities.

### Task 2 (Mar 4)

- create a 3d object (eg., a cube), create a new script and define a class descendant from MonoBehavior, add the class to the created object.
- in the class Startup method, instantiate a class that provides Ultraleap data and assing a handler to capture Ultraleap hand data
- in the class Update method, set the X object's position to the hand (palm) X position.
- find out if UltraLeap automatically detects pinch gestures. If so, modify your class so that the 3D object moves only when pinch is recognized in the right hand data.
