Benchmark Project: CPU or GPU Bound
Use Stats
aim for 60+ FPS non vr (16ms per frame), 90 FPS for VR/AR (11ms per frame)

Profiler: Shows the Game Loop- Editor and Player
Player loop should be under 20ms

Hierarchy, Raw Hierarchy Mode
CPU, Rendering, Physics

---------------------------------------------------------------------------
CPU Constraints:
low Instantiation, low Garbage collection, optimize data structures 

Scriptable objects -> same object but different configurations

Use Defines -> preprocessing directives 

remove start and update functions, remove any empty functions -> or use preprocessing directives 

make sure that you are 

avoid having havy processing logic in start and awake because it will prevent frames from rendering in the correct order 

Flatten your hierarchies -> separate those that need transformation propagation from those that don't (minimize children)

Accelerometer -> minimize accelerometer frequency if you aren't using it on mobile platforms

Rigibody -> use the rigibody.[action] functions on objects that have rigidbodies for best performance not Translate etc.

DONT call .AddComponent on runtime -> it is very innefficient, especially multiple each frame because it 
checks all components attached to the object first, very expensive checks + processes all Awake() methods adding more to the Heap
DO USE Prefabs

DONT USE GameObject.Find(..) needs to itterate across all objects in the scene at runtime incurring runtime costs
DONT USE Get.Component()
DO cache the reference to the object 
------------------------------------------------------------------------

Asset Importing 
Texture import Settings ->
DO evaluate to see if the minimum possible value will produce the best results, disable read/write 
DONT forget to adjust Mas to Min, POT (Power of Two) or Atlas, forget to remove alpha channel on opaque objects, Forget to Disable Mipmaps for UI, Forget to change 32bit to 16bit

Mesh Import Settings
DO -> Try to use more aggressive mesh compression, remove read write on static objects
DONT -> 

-------------------------------------------------------------------------

GPU Constraints:
Frames per second, Batches, Tris

Graphics, Shaders, lighting, draw calls

Stats Window, Profiler, Frame Debugger

Rendering API calls to consider:
WaitForTargetFPS
Gfx.WaitForPresent
Gfx.WaitForRenderThread
Gfx.PresentFrame
https://www.youtube.com/watch?v=uXRURWwabF4

Draw call- a set of instructions that tell the gpu how to render an image on your computer

Batching -> Submitting Draw calls to the GPU
Send as few rending calls as possible, batch more of them together, use the same materials, use the same texture
Use atlases

Dynamic Batching: reduces draw calls on moving objects (only works on messages with 900 vertex attributes) 
Dynamic batching is evaluated once per frame and this goes in the CPU

Static Batching- done at build time -> anything that wont move with be marked as static
Instantiating Static objects at runtime look at StaticBatchingUtility.Combine API

DO Minimize which objects cast shadows in complex scenes

DO Add culling masks for lights

DO minimize lights added to the scene

DO Avoid mobile native resolutions: Screen.SetResolution(width,height, false);
DO Lower default resolution, and profile multiple scenarios

DO hide invisible UI elements (set inactive) Cameras cannot cull UIs, disable if not used

DO Batch your UI -> Seperate UI elements in sub-canvases, UI elements within a canvas with the same Z value,
 Same materials and textures, Same clipping rect 