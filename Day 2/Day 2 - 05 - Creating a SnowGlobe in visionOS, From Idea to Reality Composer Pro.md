https://chaocode.notion.site/Creating-a-Snow-Globe-in-visionOS-From-Idea-to-Reality-Composer-Pro-174b8b85a1178017ac6ec9fbf8dfdc65

**3D Modeling Basic**
- From idea to model: start with all perspectives
- Draw the prototype, top down view aswell

- 2 Modelling Technique
	- Extrusion: Extending a 2D shape along a path to create a 3D object
		- SwiftUI Path Extrusion
	- Box Modelling
		- Loop Cut (Creates new faces, edges, and vertices for finer adjustments)

**Reality Composer Pro 2.0**
- Combine the 3D models in the reality composer pro
- Use Particle Effects to easily generate effects
	- Particles live in World Space
		- When you move it around, the particle follows and duplicates
	- Checkbox Particles in Local Space
- Types of Light
	- Spot Light (cone shaped)
	- Directional Light (simulating light from very far away)
	- Point Light
- Types of Audio
	- Spatial Audio (plays the sound source in specific location)
		- Rolloff Factor (how quickly the sound adjusts), the higher the value, the quieter it gets when we go far
	- Ambient Audio (fixed to a direction) (no matter where the user moves, they will always hear it in that direction)
	- Basic Audio
- Button Interaction
	- Behaviors -> OnTap -> Action
		- On Collision
		- On Added to Scene
		- On Notification
		- Action can be created in Timelines
			- Simulate pressed physics, play click sound, activate the train, transform button back
			- Notification can be used to send notification action so that we can handle the model from the source code