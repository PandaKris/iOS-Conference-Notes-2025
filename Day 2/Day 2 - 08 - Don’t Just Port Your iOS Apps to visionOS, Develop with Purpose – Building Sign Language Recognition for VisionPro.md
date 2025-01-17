
Vision Pro Capabilities
- Apps just use windows on VisionPro, what if we can leverage more on this?
- Since VisionPro is expensive, cannot just port and thats it, build it so that VisionPro is utilized

Exploring the APIs
- WorldTrackingProvider: Accurate tracking of the user's environment
- RoomTrackingProvider: More context on the room
- ObjectTrackingProvider: tracking and detecting objects in the environment
- HandTrackingProvider
- ImageTrackingProvider

ML:
- Kaggle ASL Alphabet Dataset
- MediaPipie Hands
- TensorFlow Models: InceptionNet, EfficientNet
- YOLO for Gesture Detection

Trajectory need to be calculated with the world space
- they have relative hand position

After that, use Tabular Classifier

Turns out there are movements, we now move to ActivityClassifier

Because hand movement now matters, we use the coordinate in the head as a point

Considerations:
- Expand Training Dataset
- Enhance Vocabulary
- Facial Expression

Rethink. Innovate. Develop with Purpose.