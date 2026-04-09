# Practice projects

***

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

### Task 5 (Mar 18)

- create flatter scale model and replace it in the Unity project
	- (12.3.26) Completed
- test the project in VR with Meta Quest
	- (12.3.26) Completed
- remove non-English comments from the code
	- (12.3.26) Completed

_**Supervisor's contribution:**_
- camera rendering brightness solved
- camera image flipped
- default camera's name is used instead of the fixed camera name

***

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
	- (16.3.26) Completed
- add a `Start` button to the overlay: pressing this button must hide the 2d overlay.
	- (16.3.26) Completed

### Task 3 (Mar 14)
- create a vertical plane, a black central line on this plane, and a red line on top of the black line.
	- (17.3.26) Completed
- `Settings.FieldSize` property must be equal to the plane's height.
	- (17.3.26) Completed
- both lines must be oriented vertically if `Settings.Orientation` is `Vertical`, or horizontally if `Settings.Orientation` is `Horizontal`.
	- (17.3.26) Completed

### Task 4 (Mar 17)
- install Meta Quest 3 VR (maybe also SteamVR) and investigate how it run Unity app in VR.
	- (18.3.26) Completed
	- I connected the VR headset to the computer via Bluetooth, then in the headset settings I selected Remote Desktop and chose my PC.
- transfer CTT logic into the project
    - (19.3.26) *completed by the project leader*
- bind the input position to the line position:
	- study the `Assets/Scripts/ctt/Controller` class.
	- find the places where LinePositionX and LinePositionY are changing and add a code that moves the line that you created.
 	- (20.3.26) Completed

### Task 5 (Mar 30)
- add more UI controls to the overlay to cover most of the settings (leave out anything related to tones and pathes). Colors could be specified as RGB values separated by comma.
 	- (2.4.26) Completed
- add two short threshold lines to the line movement field. One line must be placed at 1/4 and another at 3/4 of the fieldäs height (check the original app for reference: blue short lines in [this](https://www.researchgate.net/figure/Critical-tracking-task-CTT-example-screen_fig1_256446631) image).
 	- (8.4.26) Completed
- update the code so that both threshold lines and the moving line get their width (heights in vertical orientation) from the corresponding Settings class properties (threshold line are call there as "Far" lines).
 	- (8.4.26) Completed
- update the code so that all lines and the field (background) get thier colors from the corresponding Settings class properties.
 	- (8.4.26) Completed

### Task 6 (Apr 9)
- add virtual environment to the scene, so it looks like a user is standing in a room while duing the CTT task. You can find vairous furniture and even haouses on some websites for free, just download and import them. Prefer light-weighted models, so the repository (Assets folder) stays under, say, 250 Mb.
- enabled camera rotation on mouse movement.
- add several table near the CTT field (could be arrange in a circular manner: 3 tables on the left, and 3 tables on the right at the same distance from the camera)
	- a table with 4 (2x2) rectangular black boxes (or plates) with white numbers from 1 to 8 (Consult the supervisor about the exact outlook of the table)
	- similar table with 8 (2x4) boxes/plates. 
	- similar table with 9 (3x3) boxes/plates. 
	- a table with 12 (3x4) rectangular food images (banana, strawberry, lemon, etc.). 
	- a table with 9 (3x3) rectangular household images (phone, stove, etc.).
	- a table with 8 (2x8) traffic signs (use simplest from [Traffi](https://vayla.fi/en/transport-network/road-signs)).
- add the code that logs (using `Logger.Instance.Add()`) the box/plate displayed number or item name every time a user hits it using hand controller's beam. 

_**Supervisor's contribution:**_
- extraction of original CTT code
- overlay layout
- fixed usage of settings due to poorly explained task #5 

## [Valtra IMU data visualizer](https://github.com/Dimitrij000/ValtraDataVis)

### Task 1 (Mar 22)
- create a Valtra tractor model in Blender
	- (25.3.26) Completed

### Task 2 (Mar 24)
- create an empty 3D project in Unity, name it `ValtraDataVis`
	- (25.3.26) Completed
- publish the project on GitHub: make sure `.gitignore` contains the `data` folder, as data files are too heavy (data files to be obtained from the supervisor).
	- (25.3.26) Completed
- add some flat terrain, import the tractor model.
	- (25.3.26) Completed

### Task 3 (Mar 24)
- create Valtra IMU data parser.
	- (27.3.26) Completed
- create a player that moves the tractor using `Easting` and `Northing` data fields. Playback should start and pause upon pressing ENTER button. The app should ask for the file to be played when ENTER is pressed for the first time.
	- (27.3.26) Completed
- use rotation from IMU data to orient the tractor properly.
	- (7.4.26) Completed
- find and import a Unity module that allows to control the camera using mouse and keyboard.
	- (1.4.26) Completed / final edit by supervisor

### Task 4 (Apr 7)
- make the tractor's path visible: discuss the task details with the supervisor before you start.
- add some textures to the environment.
- consider enabling physics for the tractor. Report your findings in any case.
- consider creating wheel rotation animation, either at a fixed or controllable speed. Report your findings in any case.

_**Supervisor's contribution:**_
- imported the fast IMU data provider class and used its instance in TractorPlayer class replacing the code that required full IMU data loading into RAM.
