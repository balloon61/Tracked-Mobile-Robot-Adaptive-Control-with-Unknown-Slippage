# Introduction
  When the tracked mobile robot moves outside, especially on the soil, it's hard to control the robot precisely. Even if you got extremely accurate odometry feedback, estimating your pose is still very hard. One of the major issues of this problem is the slip between the track and the soil. It causes the kinematic model to be incorrect. This repository assumes an unknown slip exists in the kinematic model and uses adaptive control to find the slip while tracking the predefined trajectory adaptively.
  
## Requirement
This system is built in Simulink 2020b.

## Motor Control
  Since we need to control a motor, it's improtant to get the transfer function of the motor from system identification. After the System ID experiment, we get the motor transfer function:

![image](https://user-images.githubusercontent.com/55338365/230802756-f206ca48-2a2d-4a98-b372-f90ce29eaa0d.png)

We design a PI control to control the motor.

![image](https://user-images.githubusercontent.com/55338365/230806821-00277365-1c1c-4940-90e3-22fce7bf44dc.png)

## Control Scheme
Trajectory tracking adaptive control scheme.

![image](https://user-images.githubusercontent.com/55338365/230810011-91e29995-2742-4f67-b0f4-feaec2cb68a9.png)


## Trajectory Tracking

tracking error:

![image](https://user-images.githubusercontent.com/55338365/230810393-14a526a3-7356-488c-9c77-f470dad9bf29.png)

desired motion command tracking error

![image](https://user-images.githubusercontent.com/55338365/230809186-8c573051-8d8d-4355-8852-93d8b8eeb654.png)

## Adaptive slip tuning

slip adaptive tuning performance

![image](https://user-images.githubusercontent.com/55338365/230809533-8ffc2e57-6a7c-44af-94aa-ba1ad946bfea.png)


## Improvement
With the adaptive law, you can see the tracking error improve tremendously, and the motion command also converges to the desired command.

## Reference
 M. Cui, ‘‘Observer-based adaptive tracking control of wheeled mobile robots with unknown slipping parameters,’’ IEEE Access, vol. 7, pp. 169646–169655, 2019.
