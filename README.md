# HighPrecisionStepperJuggler
a.k.a Octo-Bouncer. Highly precise stepper motor driving with a Teensy 4.0 and custom pulse generating algorithm and PC based image processing with the goal of getting a machine to juggle a ping pong ball.

[Here's](https://electrondust.com/2020/03/01/the-octo-bouncer/) a blog post with more infos about this project. And [here's](https://youtu.be/lYyAMDYzJQM) a YouTube video of the machine in action.

The Arduino folder contains the code for the Teensy 4.0. The Teensy 4.0's job is simple:

- Listen for movement comments on the serial bus
- Generate pulses for the stepper motors

The Unity folder contains the code for the Unity Application. This Application is responsible for:

- Set up the camera (120 FPS 640×480 data stream, gain, exposure, contrast, ISO, saturation) via OpenCV
- Set up Camera Device and getting image stream via OpenCV
- Run Image Processing and get 2D pixel position of ping pong ball
- Get 3D position of ping pong ball using the results of above-mentioned image processing
- Calculate ball velocity
- Use ball position and velocity in PID/Analytical control code to calculate correction-tilt of plate
- Execute Inverse Kinematic code to figure out how much each motor needs to rotate in order to get the plate to a certain height with a     specific tilt.
- Send result of IK calculation to the microcontroller via serial interface
- Render machine position and movements
- Render image processing data
- Render graph showing several data streams

The UVCCameraPlugin folder contains the C++ code for the camera plugin. This is a Unity plugin. All the OpenCV code is being executed in here.



###
###
An Advance AI-assisted Bouncer trying to control a bouncing ball!

It is an Arduino project with 120 FPS custom image processing and smooth stepper motor moves. The machine calculates the ball's 3D position from the image processing data and uses this information to control the orange ping pong ball.

Some cool features:
- New custom ball detection algorithm
- New ball position data visualization
- Hit position prediction using gradient descent
- Plate tilt visualization
- Analytical tilt control
- Two-step bouncing

This machine requires the following things to work:
- 1x Teensy 4.0 Microcontroller
- 4x StepperOnline DM442S stepper motor drivers
- 4x Nema 17 Stepper Motors with 5:1 planetary gearbox
- 1x 48V 8A power supply
- 1x e-con Systems See3CAM_CU135 camera
- 1x Windows Computer running below Unity Application
- Custom Windows Application (made with Unity)
- All the parts defined the Fusion360 project

Read more here:
https://electrondust.com/2020/05/25/the-octo-bouncer:-advanced-bouncing-patterns/

Video:
https://dms.licdn.com/playlist/C5605AQGHEhKdQbs8Bw/mp4-720p-30fp-crf28/0?e=1592420400&v=beta&t=Nwt2T8tvQ-_v-ryo0hiLs2m8XtjPutw5C89qVx_uyoQ


#innovation #artificialintelligence #datascience
# #machinelearning #deeplearning
