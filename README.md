# Practice projects

## [Hand-controlled camera in VR](https://github.com/Dimitrij000/UltraleapCamera)

### Task 1 (Mar 2)

- Install Unity 2022, install Ultraleap 3Di SDK [software](https://www.ultraleap.com/downloads/)
	- (2.3.26) Installed Unity 2022.3.17f1, downloaded and installed the Ultraleap 3Di SDK.

- Create empty VR project
  	- (3.3.26) I created a Unity VR project called “Hand‑controlled Camera in VR.”

- Add Ultraleap package as described [here]( https://docs.ultraleap.com/xr-and-tabletop/xr/unity/getting-started/index.html)
  	- (3.3.26) I went to Project Settings → Package Manager and entered the Name, URL, and Scope.
	Then, in the Window menu, I installed Ultraleap Tracking and imported the Tabletop Examples from the Samples section.
	After that, in Project Settings → XR Plug‑in Management → OpenXR, I enabled Ultraleap Hand Tracking.
  	- Issues: The first time, I installed several other unnecessary items in the Window section, so it didn’t work. That’s why I created the project again the second time, and then it worked.

- Open the "Tabletop Example" project from the package's "Samples" section
 	- (3.3.26) Completed

- Compile and run the project, and ensure the virtual hands are reflecting hand movements.
  	- (3.3.26) The hands are displayed in Unity in real time: https://drive.google.com/file/d/1Y_gJpbP6QvHLoNCBNTestix89OaoeZtd/view?usp=sharing

- Follow [the instructions](https://docs.ultraleap.com/xr-and-tabletop/xr/unity/getting-started/your-first-project.html) to add hand rigs to you own project.
	- (4.3.26) Completed

- Study [Ultraleap Plugin features](https://docs.ultraleap.com/xr-and-tabletop/xr/unity/plugin/index.html) to learns hand tracking capabilities.
	- (4.3.26) Completed

### Task 2 (Mar 4)

- create a 3d object (eg., a cube), create a new script and define a class descendant from MonoBehavior, add the class to the created object.
	- (4.3.26) I created a new 3D cube, assigned a script component to it, and inserted the code.

- in the class Startup method, instantiate a class that provides Ultraleap data and assing a handler to capture Ultraleap hand data
	- (5.3.26) Completed. 
  	- Issues: At first, I was writing the code for the new version of Ultraleap, and only later realized the mistake and switched to the old version.

- in the class Update method, set the X object's position to the hand (palm) X position.
	- (5.3.26) Completed. 
  	- Issues: At first, I was writing the code for the new version of Ultraleap, and only later realized the mistake and switched to the old version.

- find out if UltraLeap automatically detects pinch gestures. If so, modify your class so that the 3D object moves only when pinch is recognized in the right hand data.
	- (5.3.26) I added the condition if (!hand.IsPinching()) return; to the code.

### Task 3 (Mar 6)

- create a plane, create a new script and define a class CameraRenderer descendant from MonoBehavior, add the class to the created object. In the class Startup method, instantiate a class that captures frames from the default camera. In the class Update method, obtain a camera frame and render it the plane.
	- (9.3.26) I added a new script to the plane, added the code, and dragged the plane into the cube’s provider. I also connected the camera that sends the image to the plane.

- modify the HandFollower class so that it scales (shrinks or stretches out) the plane with the camera image, but only if the hand's pinch gesture is active. Note that the сцалинг operation must be relative to the current plane's scale, i.e. the pinch itself does not scale the plane, only the hand movement after the pinch scales it.
	- (9.3.26) I added a new script to the plane, added the code, and dragged the plane into the cube’s provider. I also connected the camera that sends the image to the plane.

### Task 4 (Mar 10)

- in CameraPlane class, limit the scaling so that X plane scale stays within the range from 0.1 to 10.
	- (10.3.26) I limited the object's movement, which also restricted the plane’s scalability.
- add some 3D shape ("scale"), long and narrow, that is placed below the camera plane along its bottom edge. Replace the hand-following cube with some nice-looking knob. Find such a shape and the knob in free FBX libraries, or use Blender to create them.
	- (10.3.26) I changed the cube to a 3D gear.
- modify the code in HandFollower class so that the knob represents the X scale of CameraPlane. The knob should move over the scale only.
	- (10.3.26) Completed
- study animations in Unity, and try to create some simple animation for the knob.
	- (11.3.26) Completed
- spend some time to figure out how to make the camera rendering brighter.
	- (11.3.26) Completed
- create a github project, add it to the list of remotes in your local git repo, commit all unsaved changes, and push the project to the github.
  	- (11.3.26) [UltraLeap Camera](https://github.com/Dimitrij000/UltraleapCamera)

### Task 5 (Mar 17)

- create flatter scale model and replace it in the Unity project
- remove non-English comments

**Supervisor's contribution:**
- camera rendering brightness solved
- camera image flipped
- default camera's name is used instead of the fixed camera name


## [Critical Tracking Task in VR](https://github.com/Dimitrij000/CttVR)

### Task 1 (Mar 12)
- clone [CTT project](https://github.com/lexasss/ctt) and study how it works.
	- (12.3.26) Completed
- create an empty VR project in Unity, name it `CttVr`.
	- (12.3.26) Completed
- copy the `Settings.cs` file from the CTT project to Unity's `Assets\Scripts` folder. Remove `INotifyPropertyChanged`, make all public properties as simple `{ get; set; }` properties.
	- (12.3.26) Completed
- modify the rest of the `Settings` class implementation so that it can be compiled.
	- (12.3.26) Completed
- note that is automatic properties storage (as it is implemented in `Settings.cs`) is not available in Unity, then implement custom loading/saving of `Settings` public properties from/to `settings.json` file stored in `Environment.SpecialFolder.LocalApplicationData`.
	- (12.3.26) Completed

### Task 2 (Mar 13)
- create a 2d overlay with input controls to select the input type and orientation. Bind values of these combo-box controls to `Input` and `Orientation` properties of the `Settings` class.
- add a `Start` button to the overlay: pressing this button must hide the 2d overlay.

### Task 3 (Mar 14)
- create a vertical plane, a black central line on this plane, and a red line on top of the black line.
- `Settings.FieldSize` property must be equal to the plane's height.
- both lines must be oriented vertically if `Settings.Orientation` is `Vertical`, or horizontally if `Settings.Orientation` is `Horizontal`.
- bind the input position to the red line position: use the files from the original CTT applicaiton to get mouse, keyboard and joystick input, and also the logic that moves the red line.
