# Body_detection_through_mediapipe
<h1>Overview

<h5>Live perception of simultaneous human pose, face landmarks, and hand tracking in real-time on mobile devices can enable various modern life applications: fitness and sport analysis, gesture control and sign language recognition, augmented reality try-on and effects. MediaPipe already offers fast and accurate, yet separate, solutions for these tasks. Combining them all in real-time into a semantically consistent end-to-end solution is a uniquely difficult problem requiring simultaneous inference of multiple, dependent neural networks.

  
<h1>ML Pipeline
 <h5>The MediaPipe Holistic pipeline integrates separate models for pose, face and hand components, each of which are optimized for their particular domain. However, because of their different specializations, the input to one component is not well-suited for the others. The pose estimation model, for example, takes a lower, fixed resolution video frame (256x256) as input. But if one were to crop the hand and face regions from that image to pass to their respective models, the image resolution would be too low for accurate articulation. Therefore, we designed MediaPipe Holistic as a multi-stage pipeline, which treats the different regions using a region appropriate image resolution
  
<h1> Steps for the Installation
<h6>-First install the mediapipe liberary and open cv(computer vision) for the image detection
<h6>-second we have to to intialize the function of holistic function from the mediapipe liberary 
<h6>-third we have to acces the local cam through python and intiize the frame and then convert RGB image to the BGR & name that local camera as the 'Raw camera Feed' and then adding the relese command to relese the camera .
<h6>- Forth we have to create a function of mediapipe holistic for detection and tracking for the model detection and we are setting this as  a 0.5 for the normal clearity and when you want a good quality for the detection you can increase the value and the function is "with mp_holistic.Holistic(min_detection_confidence=0.5, min_tracking_confidence=0.5) as holistic:"
<h6>-Fifth we have to use the mp.drawing function to drow the landmarks and then we have to use the face ,pose and hand gestures by thses commands 
        "# Draw face landmarks
        mp_drawing.draw_landmarks(image, results.face_landmarks, mp_holistic.FACEMESH_TESSELATION)
        
        # Right hand
        mp_drawing.draw_landmarks(image, results.right_hand_landmarks, mp_holistic.HAND_CONNECTIONS)

        # Left Hand
        mp_drawing.draw_landmarks(image, results.left_hand_landmarks, mp_holistic.HAND_CONNECTIONS)

        # Pose Detections
        mp_drawing.draw_landmarks(image, results.pose_landmarks, mp_holistic.POSE_CONNECTIONS)"
  <h6>-after that we have to style the detection line by color, thickness , radius.
  
