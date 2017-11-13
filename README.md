# Unscented Kalman Filter Project Starter Code
Self-Driving Car Engineer Nanodegree Program

## Compiling & running

I developed it in MacOS, checkout my code and cd to that directory.

1. mkdir build
2. cd build
3. cmake ..
4. make
5. ./UnscentedKF

## Accuracy

With the dataset 1, my final RMSE is X: 0.0692, Y: 0.0867, VX: 0.3246, VY: 0.2793.

![Simulator image](/sim_ss.png)

## Flow

I modified ukf.cpp and tools.cpp. In the tools.cpp, I reused the one in the EKF project. They are identical.

In the ukf.cpp, the entry point is ProcessMeasurement(). The main.cpp will feed new measurement through this method. When it been called in the first time, I trust the measurement and made up a P.

With the following measurements, I do prediction and update. In the prediction, I follow the chapter 18 in the course. In the update stage, I called UpdateLidar() or UpdateRadar() based on the type of new measurement.

These two methods were doing similar things execpt the coordinate system are different.

Overall, this one is more difficult than the EKF. Although most code snippets were provided in the course, there are still a lot places need to modify. It's a good experience to practice.